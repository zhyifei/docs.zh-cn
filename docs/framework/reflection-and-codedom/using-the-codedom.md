---
title: "使用 CodeDOM | Microsoft Docs"
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
  - "代码编译器"
  - "代码文档对象模型"
  - "代码文档对象模型, 图形"
  - "代码生成器"
  - "CodeDOM"
  - "CodeDOM, 图形"
  - "动态编译"
  - "动态表示源代码"
  - "使用 CodeDOM 绘图"
  - "命名空间 [.NET Framework], CodeDOM"
  - "源代码模型"
  - "模板代码生成"
  - "类型, CodeDOM"
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 使用 CodeDOM
CodeDOM 提供了表示许多常见的源代码元素类型的类型。  您可以设计一个生成源代码模型的程序，使用 CodeDOM 元素构成一个对象图。  可以使用受支持的编程语言的 CodeDOM 代码生成器，将该对象图呈现为源代码。  CodeDOM 也可以用于将源代码编译成二进制程序集。  
  
 CodeDOM 的一些一般用途包括：  
  
-   模板化代码生成：生成 ASP.NET、XML Web 服务客户端代理、代码向导、设计器或其他代码发出机制的代码。  
  
-   动态编译：支持以一种或多种语言进行代码编译。  
  
## 生成 CodeDOM 图  
 <xref:System.CodeDom> 命名空间提供表示源代码的逻辑结构（与语言语法无关）的类。  
  
### CodeDOM 图的结构  
 CodeDOM 图的结构类似于一个容器树。  每个可编译的 CodeDOM 图的最顶部（即根位置）的容器都是 <xref:System.CodeDom.CodeCompileUnit>。  源代码模型的每个元素都必须通过图中 <xref:System.CodeDom.CodeObject> 的属性链接到图中。  
  
### 为 Hello World 示例程序生成源代码模型  
 以下演练提供了一个如何生成 CodeDOM 对象图的示例，该对象图表示一个简单的应用程序 Hello World 的代码。  要获得此代码示例的完整源代码，请参见 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName> 主题。  
  
#### 创建编译单元  
 CodeDOM 定义一个名为 <xref:System.CodeDom.CodeCompileUnit> 的对象，该对象可以引用对要编译的源代码进行建模的 CodeDOM 对象图。  **CodeCompileUnit** 具有存储对特性、命名空间和程序集的引用的属性。  
  
 从 <xref:System.CodeDom.Compiler.CodeDomProvider> 类中派生的 CodeDom 提供程序包含用于处理 **CodeCompileUnit** 所引用的对象图的方法。  
  
 要创建简单应用程序的对象图，必须汇编源代码模型并从 **CodeCompileUnit** 引用它。  
  
 您可以用本示例中示范的语法创建一个新的编译单元：  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <xref:System.CodeDom.CodeSnippetCompileUnit> 可以包含已经以目标语言表示的源代码段，但不能呈现为另一种语言。  
  
#### 定义命名空间  
 若要定义命名空间，请创建一个 <xref:System.CodeDom.CodeNamespace>，并使用适当的构造函数或通过设置其 **Name** 属性为它赋予一个名称。  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### 导入命名空间  
 若要将命名空间的导入指令添加到命名空间，请添加 <xref:System.CodeDom.CodeNamespaceImport>，它指示要导入到 **CodeNamespace.Imports** 集合的命名空间。  
  
 下面的代码将 **System** 命名空间的导入指令添加到名为 `samples` 的 **CodeNamespace** 的 **Imports** 集合：  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### 将代码元素链接到对象图中  
 构成 CodeDOM 图的所有代码元素都必须通过元素间直接从图的根对象属性引用的一系列引用链接到 <xref:System.CodeDom.CodeCompileUnit>（树的根元素）。  将对象设置为容器对象的属性以便从容器对象建立引用。  
  
 下面的语句将 `samples` **CodeNamespace** 添加到根位置 **CodeCompileUnit** 的 **Namespaces** 集合属性。  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### 定义类型  
 若要用 CodeDOM 声明类、结构、接口或枚举，请创建一个新的 <xref:System.CodeDom.CodeTypeDeclaration>，并为它赋予一个名称。  下面的示例通过用构造函数重载设置 **Name** 属性来说明这一点：  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 若要将类型添加到命名空间，请添加 <xref:System.CodeDom.CodeTypeDeclaration>，它表示要添加到 **CodeNamespace** 的 **Types** 集合的命名空间的类型。  
  
 下面的示例演示了如何将名为 `class1` 的类添加到名为 `samples` 的 **CodeNamespace**：  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### 将类成员添加到类  
 <xref:System.CodeDom> 命名空间提供了多种可用来表示类成员的元素。  每个类成员都可以添加到 <xref:System.CodeDom.CodeTypeDeclaration> 的 **Members** 集合。  
  
#### 定义可执行程序的代码入口点方法  
 如果生成可执行程序的代码，必须指示程序的入口点，具体做法是创建一个 <xref:System.CodeDom.CodeEntryPointMethod> 来表示应从哪个方法开始执行程序。  
  
 下面的示例演示如何定义入口点方法（该方法包含调用 **System.Console.WriteLine** 以打印“Hello World\!”的 <xref:System.CodeDom.CodeMethodInvokeExpression>）：  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 下面的语句将名为 `Start` 的入口点方法添加到 `class1` 的 **Members** 集合：  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 现在，名为 `compileUnit` 的 <xref:System.CodeDom.CodeCompileUnit> 包含简单的 Hello World 程序的 CodeDOM 图。  有关从 CodeDOM 图生成和编译代码的信息，请参见[生成源代码和在 CodeDOM 图中编译程序](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)。  
  
### 关于生成 CodeDOM 图的更多信息  
 CodeDOM 支持许多常见的代码元素类型，这些代码元素出现在支持公共语言运行时的编程语言中。  CodeDOM 不会为表示各种可能的编程语言功能而提供相应元素。  不容易用 CodeDOM 元素表示的代码可以封装在 <xref:System.CodeDom.CodeSnippetExpression>、<xref:System.CodeDom.CodeSnippetStatement>、<xref:System.CodeDom.CodeSnippetTypeMember> 或 <xref:System.CodeDom.CodeSnippetCompileUnit> 中。  但是，CodeDOM 无法自动将代码段转换为其他语言。  
  
 有关每个 CodeDOM 类型的文档，请参见 <xref:System.CodeDom> 命名空间的参考文档。  
  
 有关定位表示特定代码元素类型的 CodeDOM 元素的速查表，请参见 [CodeDOM Quick Reference](http://msdn.microsoft.com/zh-cn/c77b8bfd-0a32-4e36-b59a-4f687f32c524)。