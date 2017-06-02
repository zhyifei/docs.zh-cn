---
title: "如何：使用 CodeDOM 创建类 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "代码文档对象模型, 创建类"
  - "代码文档对象模型, 图形"
  - "CodeDOM, 创建类"
  - "CodeDOM, 图形"
  - "使用 CodeDOM 绘图"
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 如何：使用 CodeDOM 创建类
下面的过程说明如何创建和编译 CodeDOM 关系图，这个关系图用于生成由以下各项组成的类：两个字段、三个属性、一个方法、一个构造函数和一个入口点。  
  
1.  创建将使用 CodeDOM 代码生成类的源代码的控制台应用程序。  
  
     在此示例中，生成类被命名为 `Sample`，生成的代码是名为 SampleCode 的文件中的一个名为 `CodeDOMCreatedClass` 的类。  
  
2.  在生成类中初始化 CodeDOM 关系图，并使用 CodeDOM 方法定义生成的类的成员、构造函数和入口点（`Main` 方法）。  
  
     在此示例中，生成的类包含两个字段、三个属性、一个构造函数、一个方法和一个 `Main` 方法。  
  
3.  在生成类中创建一个语言特定代码提供程序，并调用它的 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法从关系图生成代码。  
  
4.  编译和执行应用程序以生成代码。  
  
     在此示例中，生成的代码位于名为 SampleCode 的文件中。  编译并执行此代码，以查看样本输出。  
  
### 创建将执行 CodeDOM 代码的应用程序  
  
-   创建要包含 CodeDOM 代码的控制台应用程序类。  定义该应用程序类中使用的全局字段，以便引用程序集 \(<xref:System.CodeDom.CodeCompileUnit>\) 和类 \(<xref:System.CodeDom.CodeTypeDeclaration>\)；指定生成的源文件的名称，并声明 `Main` 方法。  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### 初始化 CodeDOM 关系图  
  
-   在控制台应用程序类的构造函数中，初始化程序集和类，并为 CodeDOM 关系图添加适当的声明。  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### 向 CodeDOM 关系图添加成员  
  
-   将 <xref:System.CodeDom.CodeMemberField> 对象添加到类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性，从而向 CodeDOM 关系图添加字段。  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
-   将 <xref:System.CodeDom.CodeMemberProperty> 对象添加到类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性，从而向 CodeDOM 关系图添加属性。  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
-   将 <xref:System.CodeDom.CodeMemberMethod> 对象添加到类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性，从而向 CodeDOM 关系图添加方法。  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
-   将 <xref:System.CodeDom.CodeConstructor> 对象添加到类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性，从而向 CodeDOM 关系图添加构造函数。  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
-   将 <xref:System.CodeDom.CodeEntryPointMethod> 对象添加到类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性，从而向 CodeDOM 关系图添加入口点。  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### 从 CodeDOM 关系图生成代码  
  
-   调用 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法以便从 CodeDOM 关系图生成源代码。  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### 创建关系图并生成代码  
  
1.  将以上步骤中创建的方法添加到第一步中定义的 `Main` 方法中。  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2.  编译和执行生成类。  
  
## 示例  
 下面的代码示例显示上述步骤中的代码。  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 编译和执行以上示例后，会生成下面的源代码。  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 生成的源代码经过编译和执行以后，产生下面的输出。  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## 编译代码  
  
-   要成功执行此代码示例，就需要设置 `FullTrust` 权限。  
  
## 请参阅  
 [使用 CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)   
 [在 CodeDOM 图中生成和编译源代码](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)