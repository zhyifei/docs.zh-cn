---
title: "在 CodeDOM 图中生成和编译源代码 | Microsoft Docs"
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
  - "程序集 [.NET Framework], CodeDOM"
  - "代码编译器"
  - "代码文档对象模型, 生成源代码"
  - "代码文档对象模型, 图形"
  - "代码生成器"
  - "CodeDOM, 生成源代码"
  - "CodeDOM, 图形"
  - "编译程序集"
  - "编译源代码, 多种语言"
  - "动态编译"
  - "动态表示源代码"
  - "生成 CodeDOM 图形"
  - "用多种语言生成源代码"
  - "使用 CodeDOM 绘图"
  - "通过 CodeDOM 输出源代码"
  - "源代码生成"
  - "源代码, 生成"
  - "模板代码生成"
  - "将一种语言翻译成另一种"
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# 在 CodeDOM 图中生成和编译源代码
<xref:System.CodeDom.Compiler> 命名空间提供了从 CodeDOM 对象图生成源代码和用受支持的编译器管理编译的接口。  代码生成器可以按照 CodeDOM 图，用某种编程语言生成源代码。  从 <xref:System.CodeDom.Compiler.CodeDomProvider> 派生的类通常可以提供一些方法，用于生成和编译提供程序支持的语言的代码。  
  
## 使用 CodeDOM 代码生成器生成源代码  
 要用某种语言生成源代码，需要一个表示要生成的源代码的结构的 CodeDOM 图。  
  
 下面的示例演示如何创建 <xref:Microsoft.CSharp.CSharpCodeProvider> 的实例：  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 代码生成图通常包含在 <xref:System.CodeDom.CodeCompileUnit> 中。  若要为包含 CodeDOM 图的 **CodeCompileUnit** 生成代码，请调用代码提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法。  此方法有一个可用来生成源代码的 <xref:System.IO.TextWriter> 参数，因此，有时需要首先创建一个可以写入的 **TextWriter**。  下面的示例演示了如何从 **CodeCompileUnit** 生成代码以及如何将生成的源代码写入名为 HelloWorld.cs 的文件。  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## 使用 CodeDOM 代码提供程序编译程序集  
 **调用编译**  
  
 若要使用 CodeDom 提供程序编译程序集，必须有要用某种有编译器的语言编译的源代码，或者有 CodeDOM 图（可用来生成要编译的源代码）。  
  
 如果从 CodeDOM 图进行编译，请将包含该图的 <xref:System.CodeDom.CodeCompileUnit> 传递给代码提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> 方法。  如果您具有使用编译器可以理解的语言编写的源代码文件，请将包含源代码的文件的名称传递给 CodeDom 提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 方法。  也可以将包含用编译器识别的语言编写的源代码的字符串传递给 CodeDom 提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> 方法。  
  
 **配置编译参数**  
  
 CodeDom 提供程序的所有标准编译\-调用方法都有一个 <xref:System.CodeDom.Compiler.CompilerParameters> 类型的参数，该参数指示用于编译的选项。  
  
 可以在 **CompilerParameters** 的 <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> 属性中指定输出程序集的文件名。  否则，将使用默认的输出文件名。  
  
 默认情况下，新的 **CompilerParameters** 在初始化时其 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> 属性被设置为 **false**。  如果编译可执行程序，必须将 **GenerateExecutable** 属性设置为 **true**。  当 **GenerateExecutable** 设置为 **false** 时，编译器将生成一个类库。  
  
 如果要从 CodeDOM 图编译可执行文件，则必须在该图中定义 <xref:System.CodeDom.CodeEntryPointMethod>。  如果有多个代码入口点，可能需要将 **CompilerParameters** 的 <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> 属性设置为定义要使用的入口点的类名。  
  
 若要将调试信息包含在生成的可执行文件中，请将 <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> 属性设置为 **true**。  
  
 如果您的项目引用了任何程序集，必须将作为 <xref:System.Collections.Specialized.StringCollection> 中的项的程序集名称指定为调用编译时使用的 **CompilerParameters** 的 <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> 属性。  
  
 通过将 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> 属性设置为 **true**，可以编译写入内存而不是磁盘中的程序集。  当在内存中生成程序集时，代码可从 <xref:System.CodeDom.Compiler.CompilerResults> 的 <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> 属性中获取对生成的程序集的引用。  如果程序集写入磁盘，可从 **CompilerResults** 的 <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> 属性中获取生成的程序集的路径。  
  
 若要指定调用编译进程时要使用的自定义命令行参数字符串，请在 <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 属性中设置该字符串。  
  
 如果在调用编译器进程时需要 Win32 安全标记，请在 <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> 属性中指定该标记。  
  
 若要将一个 Win32 资源文件链接到已编译的程序集中，请在 <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> 属性中指定该 Win32 资源文件的名称。  
  
 若要指定暂停编译的警告等级，请将 <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> 属性设置为一个用来表示暂停编译的警告等级的整数。  也可以通过将 <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> 属性设置为 **true**，将编译器配置为在遇到警告时暂停编译。  
  
 下面的代码示例演示如何使用从 <xref:System.CodeDom.Compiler.CodeDomProvider> 类派生的 CodeDom 提供程序编译源文件。  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## 原本即受支持的语言  
 .NET framework 为下列语言提供代码编译器和代码生成器:C\#、 Visual Basic、 C\+\+ 和 JScript。  通过实现专用于特定语言的代码生成器和代码编译器，CodeDOM 支持可以扩展到其他语言。  
  
## 请参阅  
 <xref:System.CodeDom>   
 <xref:System.CodeDom.Compiler>   
 [动态源代码生成和编译](../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)   
 [CodeDOM Quick Reference](http://msdn.microsoft.com/zh-cn/c77b8bfd-0a32-4e36-b59a-4f687f32c524)