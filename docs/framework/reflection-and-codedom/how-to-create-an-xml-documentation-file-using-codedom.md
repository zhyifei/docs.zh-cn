---
title: "如何：使用 CodeDOM 创建 XML 文档文件 | Microsoft Docs"
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
  - "代码文档对象模型, 生成 XML 文档"
  - "CodeDOM, 生成 XML 文档"
  - "XML 文档, 使用 CodeDOM 创建"
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 如何：使用 CodeDOM 创建 XML 文档文件
CodeDOM 可用于创建生成 XML 文档的代码。  该进程包括创建包含 XML 文档注释的 CodeDOM 关系图、生成代码和通过创建 XML 文档输出的编译器选项编译生成的代码。  
  
### 创建包含 XML 文档注释的 CodeDOM 关系图  
  
1.  为示例应用程序创建包含 CodeDOM 关系图的 <xref:System.CodeDom.CodeCompileUnit>。  
  
2.  使用 <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> 构造函数（`docComment` 参数设置为 `true`）创建 XML 文档注释元素和文本。  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### 从 CodeCompileUnit 生成代码  
  
1.  使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法生成代码并创建要编译的源文件。  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### 编译代码和生成文档文件  
  
1.  将 **\/doc** 编译器选项添加到 <xref:System.CodeDom.Compiler.CompilerParameters> 对象的 <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 属性中，然后将该对象传递给 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 方法，以便在编译代码后创建 XML 文档文件。  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## 示例  
 下面的代码示例创建了一个包含文档注释的 CodeDOM 关系图，然后从该关系图生成一个代码文件，之后编译了该文件并创建了一个关联的 XML 文档文件。  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 该代码示例在 HelloWorldDoc.xml 文件中创建了下面的 XML 文档。  
  
```  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## 编译代码  
  
-   要成功执行此代码示例，就需要设置 `FullTrust` 权限。  
  
## 请参阅  
 [使用 XML 将代码文档化](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [XML 文档注释](../Topic/XML%20Documentation%20Comments%20\(C%23%20Programming%20Guide\).md)   
 [XML 文档](../Topic/XML%20Documentation%20\(Visual%20C++\).md)