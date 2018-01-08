---
title: "在 CodeDOM 图中生成和编译源代码"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56e2effec282900101fc0cbe489c76b523184ab2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a><span data-ttu-id="ad021-102">在 CodeDOM 图中生成和编译源代码</span><span class="sxs-lookup"><span data-stu-id="ad021-102">Generating and Compiling Source Code from a CodeDOM Graph</span></span>
<span data-ttu-id="ad021-103"><xref:System.CodeDom.Compiler> 命名空间提供了从 CodeDOM 对象图生成源代码和用受支持的编译器管理编译的接口。</span><span class="sxs-lookup"><span data-stu-id="ad021-103">The <xref:System.CodeDom.Compiler> namespace provides interfaces for generating source code from CodeDOM object graphs and for managing compilation with supported compilers.</span></span> <span data-ttu-id="ad021-104">代码提供程序可根据 CodeDOM 图，用某种编程语言生成源代码。</span><span class="sxs-lookup"><span data-stu-id="ad021-104">A code provider can produce source code in a particular programming language according to a CodeDOM graph.</span></span> <span data-ttu-id="ad021-105">从 <xref:System.CodeDom.Compiler.CodeDomProvider> 派生的类通常可以提供一些方法，用于生成和编译提供程序支持的语言代码。</span><span class="sxs-lookup"><span data-stu-id="ad021-105">A class that derives from <xref:System.CodeDom.Compiler.CodeDomProvider> can typically provide methods for generating and compiling code for the language the provider supports.</span></span>  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a><span data-ttu-id="ad021-106">使用 CodeDOM 代码提供程序生成源代码</span><span class="sxs-lookup"><span data-stu-id="ad021-106">Using a CodeDOM code provider to generate source code</span></span>  
 <span data-ttu-id="ad021-107">若要用某种语言生成源代码，需要一个表示要生成的源代码的结构的 CodeDOM 图。</span><span class="sxs-lookup"><span data-stu-id="ad021-107">To generate source code in a particular language, you need a CodeDOM graph that represents the structure of the source code to generate.</span></span>  
  
 <span data-ttu-id="ad021-108">下面的示例演示如何创建 <xref:Microsoft.CSharp.CSharpCodeProvider> 的实例:</span><span class="sxs-lookup"><span data-stu-id="ad021-108">The following example demonstrate how to create an instance of a <xref:Microsoft.CSharp.CSharpCodeProvider>:</span></span>  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 <span data-ttu-id="ad021-109">代码生成图通常包含在 <xref:System.CodeDom.CodeCompileUnit> 中。</span><span class="sxs-lookup"><span data-stu-id="ad021-109">The graph for code generation is typically contained in a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="ad021-110">若要为包含 CodeDOM 图的 **CodeCompileUnit** 生成代码，请调用代码提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ad021-110">To generate code for a **CodeCompileUnit** that contains a CodeDOM graph, call the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method of the code provider.</span></span> <span data-ttu-id="ad021-111">此方法有一个可用于生成源代码的 <xref:System.IO.TextWriter> 参数，因此，有时需要首先创建一个可以写入的 **TextWriter**。</span><span class="sxs-lookup"><span data-stu-id="ad021-111">This method has a parameter for a <xref:System.IO.TextWriter> that it uses to generate the source code, so it is sometimes necessary to first create a **TextWriter** that can be written to.</span></span> <span data-ttu-id="ad021-112">下面的示例演示了如何从 CodeCompileUnit 生成代码以及如何将生成的源代码写入名为 HelloWorld.cs 的文件。</span><span class="sxs-lookup"><span data-stu-id="ad021-112">The following example demonstrates generating code from a **CodeCompileUnit** and writing the generated source code to a file named HelloWorld.cs.</span></span>  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a><span data-ttu-id="ad021-113">使用 CodeDOM 代码提供程序编译程序集</span><span class="sxs-lookup"><span data-stu-id="ad021-113">Using a CodeDOM code provider to compile assemblies</span></span>  
 <span data-ttu-id="ad021-114">**调用编译**</span><span class="sxs-lookup"><span data-stu-id="ad021-114">**Invoking compilation**</span></span>  
  
 <span data-ttu-id="ad021-115">若要使用 CodeDom 提供程序编译程序集，则要编译的源代码的语言必须适用于编辑器，或者具有能够生成要编译的源代码的 CodeDOM 图。</span><span class="sxs-lookup"><span data-stu-id="ad021-115">To compile an assembly using a CodeDom provider, you must have either source code to compile in a language for which you have a compiler, or a CodeDOM graph that source code to compile can be generated from.</span></span>  
  
 <span data-ttu-id="ad021-116">如果从 CodeDOM 图进行编译，请将包含该图的 <xref:System.CodeDom.CodeCompileUnit> 传递给代码提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ad021-116">If you are compiling from a CodeDOM graph, pass the <xref:System.CodeDom.CodeCompileUnit> containing the graph to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> method of the code provider.</span></span> <span data-ttu-id="ad021-117">如果具有采用编译器可以理解的语言编写的源代码文件，请将包含源代码的文件的名称传递给 CodeDom 提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ad021-117">If you have a source code file in a language that the compiler understands, pass the name of the file containing the source code to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method of the CodeDom provider.</span></span> <span data-ttu-id="ad021-118">也可以将字符串（其中包含使用编译器可以理解的语言编写的源代码）传递给 CodeDom 提供程序的 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ad021-118">You can also pass a string containing source code in a language that the compiler understands to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> method of the CodeDom provider.</span></span>  
  
 <span data-ttu-id="ad021-119">**配置编译参数**</span><span class="sxs-lookup"><span data-stu-id="ad021-119">**Configuring compilation parameters**</span></span>  
  
 <span data-ttu-id="ad021-120">CodeDom 提供程序的所有标准编译-调用方法都有一个 <xref:System.CodeDom.Compiler.CompilerParameters> 类型的参数，指示用于编译的选项。</span><span class="sxs-lookup"><span data-stu-id="ad021-120">All of the standard compilation-invoking methods of a CodeDom provider have a parameter of type <xref:System.CodeDom.Compiler.CompilerParameters> that indicates the options to use for compilation.</span></span>  
  
 <span data-ttu-id="ad021-121">可以在 CompilerParameters 的 <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> 属性中指定输出程序集的文件名。</span><span class="sxs-lookup"><span data-stu-id="ad021-121">You can specify a file name for the output assembly in the <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> property of the **CompilerParameters**.</span></span> <span data-ttu-id="ad021-122">否则，将使用默认的输出文件名。</span><span class="sxs-lookup"><span data-stu-id="ad021-122">Otherwise, a default output file name will be used.</span></span>  
  
 <span data-ttu-id="ad021-123">默认情况下，新的 CompilerParameters 在初始化时，其 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> 属性将设置为 false。</span><span class="sxs-lookup"><span data-stu-id="ad021-123">By default, a new **CompilerParameters** is initialized with its <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> property set to **false**.</span></span> <span data-ttu-id="ad021-124">如果编译可执行程序，必须将 GenerateExecutable 属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="ad021-124">If you are compiling an executable program, you must set the **GenerateExecutable** property to **true**.</span></span> <span data-ttu-id="ad021-125">GenerateExecutable 设置为 false 时，编译器将生成类库。</span><span class="sxs-lookup"><span data-stu-id="ad021-125">When the **GenerateExecutable** is set to **false**, the compiler will generate a class library.</span></span>  
  
 <span data-ttu-id="ad021-126">如果要从 CodeDOM 图编译可执行文件，则必须在该图中定义 <xref:System.CodeDom.CodeEntryPointMethod>。</span><span class="sxs-lookup"><span data-stu-id="ad021-126">If you are compiling an executable from a CodeDOM graph, a <xref:System.CodeDom.CodeEntryPointMethod> must be defined in the graph.</span></span> <span data-ttu-id="ad021-127">如果有多个代码入口点，可能需要将 **CompilerParameters** 的 <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> 属性设置为定义要使用的入口点的类名。</span><span class="sxs-lookup"><span data-stu-id="ad021-127">If there are multiple code entry points, it may be necessary to set the <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> property of the **CompilerParameters** to the name of the class that defines the entry point to use.</span></span>  
  
 <span data-ttu-id="ad021-128">若要将调试信息包含在生成的可执行文件中，请将 <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> 属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="ad021-128">To include debug information in a generated executable, set the <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> property to **true**.</span></span>  
  
 <span data-ttu-id="ad021-129">如果项目引用了任何程序集，必须将作为 <xref:System.Collections.Specialized.StringCollection> 中的项的程序集名称指定为调用编译时使用的 **CompilerParameters** 的 <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="ad021-129">If your project references any assemblies, you must specify the assembly names as items in a <xref:System.Collections.Specialized.StringCollection> as the <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> property of the **CompilerParameters** you use when invoking compilation.</span></span>  
  
 <span data-ttu-id="ad021-130">通过将 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> 属性设置为 true，可以编译写入内存而不是磁盘中的程序集。</span><span class="sxs-lookup"><span data-stu-id="ad021-130">You can compile an assembly that is written to memory rather than disk by setting the <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> property to **true**.</span></span> <span data-ttu-id="ad021-131">在内存中生成程序集时，代码可从 <xref:System.CodeDom.Compiler.CompilerResults> 的 <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> 属性中获取对生成的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="ad021-131">When an assembly is generated in memory, your code can obtain a reference to the generated assembly from the <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> property of a <xref:System.CodeDom.Compiler.CompilerResults>.</span></span> <span data-ttu-id="ad021-132">如果程序集写入磁盘，可从 **CompilerResults** 的 <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> 属性中获取生成的程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="ad021-132">If an assembly is written to disk, you can obtain the path to the generated assembly from the <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> property of a **CompilerResults**.</span></span>  
  
 <span data-ttu-id="ad021-133">若要指定在调用编译进程时使用的自定义命令行参数字符串，请在 <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 属性中设置该字符串。</span><span class="sxs-lookup"><span data-stu-id="ad021-133">To specify a custom command-line arguments string to use when invoking the compilation process, set the string in the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property.</span></span>  
  
 <span data-ttu-id="ad021-134">如果在调用编译器进程时需要 Win32 安全令牌，请在 <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> 属性中指定该令牌。</span><span class="sxs-lookup"><span data-stu-id="ad021-134">If a Win32 security token is required to invoke the compiler process, specify the token in the <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> property.</span></span>  
  
 <span data-ttu-id="ad021-135">若要将 Win32 资源文件链接到编译的程序集，请在 <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> 属性中指定该 Win32 资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ad021-135">To link a Win32 resource file into the compiled assembly, specify the name of the Win32 resource file in the <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> property.</span></span>  
  
 <span data-ttu-id="ad021-136">若要指定暂停编译的警告等级，请将 <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> 属性设置为一个整数，表示暂停编译的警告等级。</span><span class="sxs-lookup"><span data-stu-id="ad021-136">To specify a warning level at which to halt compilation, set the <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> property to an integer that represents the warning level at which to halt compilation.</span></span> <span data-ttu-id="ad021-137">也可以通过将 <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> 属性设置为 true，将编译器配置为在遇到警告时暂停编译。</span><span class="sxs-lookup"><span data-stu-id="ad021-137">You can also configure the compiler to halt compilation if warnings are encountered by setting the <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> property to **true**.</span></span>  
  
 <span data-ttu-id="ad021-138">下面的代码示例演示如何使用从 <xref:System.CodeDom.Compiler.CodeDomProvider> 类派生的 CodeDom 提供程序编译源文件。</span><span class="sxs-lookup"><span data-stu-id="ad021-138">The following code example demonstrates compiling a source file using a CodeDom provider derived from the <xref:System.CodeDom.Compiler.CodeDomProvider> class.</span></span>  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a><span data-ttu-id="ad021-139">获得初始支持的语言</span><span class="sxs-lookup"><span data-stu-id="ad021-139">Languages with Initial Support</span></span>  
 <span data-ttu-id="ad021-140">.NET framework 提供下列语言的代码编译器和代码生成器：C#、Visual Basic、C++ 和 JScript。</span><span class="sxs-lookup"><span data-stu-id="ad021-140">The .NET Framework provides code compilers and code generators for the following languages: C#, Visual Basic, C++, and JScript.</span></span> <span data-ttu-id="ad021-141">通过实现特定语言的代码生成器和代码编译器，CodeDOM 支持可以扩展到其他语言。</span><span class="sxs-lookup"><span data-stu-id="ad021-141">CodeDOM support can be extended to other languages by implementing language-specific code generators and code compilers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad021-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad021-142">See Also</span></span>  
 <xref:System.CodeDom>  
 <xref:System.CodeDom.Compiler>  
 [<span data-ttu-id="ad021-143">动态源代码生成和编译</span><span class="sxs-lookup"><span data-stu-id="ad021-143">Dynamic Source Code Generation and Compilation</span></span>](../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)  
 [<span data-ttu-id="ad021-144">CodeDOM 快速参考</span><span class="sxs-lookup"><span data-stu-id="ad021-144">CodeDOM Quick Reference</span></span>](http://msdn.microsoft.com/en-us/c77b8bfd-0a32-4e36-b59a-4f687f32c524)
