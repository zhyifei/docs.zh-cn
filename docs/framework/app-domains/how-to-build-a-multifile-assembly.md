---
title: "如何：生成多文件程序集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5dd9de26f083209a0e8da79562f914023e008251
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="4ccbe-102">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="4ccbe-102">How to: Build a Multifile Assembly</span></span>
<span data-ttu-id="4ccbe-103">本文章介绍如何创建多文件程序集，并提供用于说明过程中每个步骤的代码。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ccbe-104">适用于 C# 和 Visual Basic 的 Visual Studio IDE 只能用于创建单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="4ccbe-105">如果要创建多文件程序集，则必须使用命令行编译器或带有 Visual C++ 的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span>  
  
### <a name="to-create-a-multifile-assembly"></a><span data-ttu-id="4ccbe-106">创建多文件程序集</span><span class="sxs-lookup"><span data-stu-id="4ccbe-106">To create a multifile assembly</span></span>  
  
1.  <span data-ttu-id="4ccbe-107">将包含程序集中其他模块引用的命名空间的所有文件编译成代码模块。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-107">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="4ccbe-108">代码模块的默认扩展名为 .netmodule。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-108">The default extension for code modules is .netmodule.</span></span>  
  
     <span data-ttu-id="4ccbe-109">例如，假定 `Stringer` 文件具有一个名为 `myStringer` 的命名空间，其中包括一个名为 `Stringer` 的类。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-109">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="4ccbe-110">`Stringer` 类包含名为 `StringerMethod` 的方法，此方法将单独一行写入控制台。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-110">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>  
  
     <span data-ttu-id="4ccbe-111">[!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]  [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]  [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="4ccbe-111">[!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]  [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]  [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]</span></span>  
  
     <span data-ttu-id="4ccbe-112">使用下面的命令编译此代码：</span><span class="sxs-lookup"><span data-stu-id="4ccbe-112">Use the following command to compile this code:</span></span>  
  
     <span data-ttu-id="4ccbe-113">[!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]  [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]  [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="4ccbe-113">[!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]  [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]  [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]</span></span>  
  
     <span data-ttu-id="4ccbe-114">使用 **/t:** 编译器选项指定 *module* 参数，表明文件应作为模块（而不是作为程序集）编译。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-114">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="4ccbe-115">编译器生成一个名为 `Stringer.netmodule` 的模块，可将其添加到程序集中。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-115">The compiler produces a module called `Stringer.netmodule`, which can be added to an assembly.</span></span>  
  
2.  <span data-ttu-id="4ccbe-116">编译所有其他模块，使用必要的编译器选项来表明代码中引用的其他模块。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-116">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="4ccbe-117">此步骤使用 /addmodule 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-117">This step uses the **/addmodule** compiler option.</span></span>  
  
     <span data-ttu-id="4ccbe-118">在下面的示例中，名为 `Client` 的代码模块具有一个入口点 `Main` 方法，此方法引用步骤 1 中创建的 `Stringer.dll` 模块中的方法。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-118">In the following example, a code module called `Client` has an entry point `Main` method that references a method in the `Stringer.dll` module created in step 1.</span></span>  
  
     <span data-ttu-id="4ccbe-119">[!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]  [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]  [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="4ccbe-119">[!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]  [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]  [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]</span></span>  
  
     <span data-ttu-id="4ccbe-120">使用下面的命令编译此代码：</span><span class="sxs-lookup"><span data-stu-id="4ccbe-120">Use the following command to compile this code:</span></span>  
  
     <span data-ttu-id="4ccbe-121">[!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]  [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]  [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="4ccbe-121">[!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]  [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]  [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]</span></span>  
  
     <span data-ttu-id="4ccbe-122">指定 /t:module 选项，因为此模块将在以后的步骤中添加到程序集。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-122">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="4ccbe-123">指定 /addmodule 选项，因为 `Client` 中的代码引用 `Stringer.netmodule` 中的代码创建的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-123">Specify the **/addmodule** option because the code in `Client` references a namespace created by the code in `Stringer.netmodule`.</span></span> <span data-ttu-id="4ccbe-124">编译器生成一个名为 `Client.netmodule` 的模块，其中包含对另一个模块 `Stringer.netmodule` 的引用。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-124">The compiler produces a module called `Client.netmodule` that contains a reference to another module, `Stringer.netmodule`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4ccbe-125">C# 和 Visual Basic 编译器支持使用以下两种不同语法直接创建多文件程序集。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-125">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>  
    >   
    >  -   <span data-ttu-id="4ccbe-126">两次编译创建出一个双文件程序集：</span><span class="sxs-lookup"><span data-stu-id="4ccbe-126">Two compilations create a two-file assembly:</span></span>  
    >   
    >      <span data-ttu-id="4ccbe-127">[!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]  [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]  [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="4ccbe-127">[!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]  [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]  [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]</span></span>  
    > -   <span data-ttu-id="4ccbe-128">一次编译创建出一个双文件程序集：</span><span class="sxs-lookup"><span data-stu-id="4ccbe-128">One compilation creates a two-file assembly:</span></span>  
    >   
    >      <span data-ttu-id="4ccbe-129">[!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]   [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]   [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="4ccbe-129">[!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]   [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]   [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]</span></span>  
  
3.  <span data-ttu-id="4ccbe-130">使用[程序集链接器 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 来创建包含程序集清单的输出文件。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-130">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="4ccbe-131">此文件包含作为程序集组成部分的所有模块或资源的参考信息。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-131">This file contains reference information for all modules or resources that are part of the assembly.</span></span>  
  
     <span data-ttu-id="4ccbe-132">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="4ccbe-132">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="4ccbe-133">al \<module name> \<module name> …</span><span class="sxs-lookup"><span data-stu-id="4ccbe-133">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="4ccbe-134">/main:\<method name> /out:\<file name> /target:\<assembly file type></span><span class="sxs-lookup"><span data-stu-id="4ccbe-134">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>  
  
     <span data-ttu-id="4ccbe-135">在此命令中，“module name”参数指定程序集要包含的各模块的名称。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-135">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="4ccbe-136">/main: 选项指定作为程序集入口点的方法名称。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-136">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="4ccbe-137">/out: 选项指定输出文件的名称，它包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-137">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="4ccbe-138">/target: 选项指定程序集是控制台应用程序可执行文件 (.exe)、Windows 可执行文件 (.win) 还是库文件 (.lib)。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-138">The **/target:** option specifies that the assembly is a console application executable (.exe) file, a Windows executable (.win) file, or a library (.lib) file.</span></span>  
  
     <span data-ttu-id="4ccbe-139">在下面的示例中，Al.exe 创建一个程序集，该程序集是一个控制台应用程序可执行文件，名为 `myAssembly.exe`。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-139">In the following example, Al.exe creates an assembly that is a console application executable called `myAssembly.exe`.</span></span> <span data-ttu-id="4ccbe-140">该应用程序由名为 `Client.netmodule` 和 `Stringer.netmodule` 的两个模块以及名为 `myAssembly.exe,`（其中只包含程序集元数据）的可执行文件组成。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-140">The application consists of two modules called `Client.netmodule` and `Stringer.netmodule`, and the executable file called `myAssembly.exe,` which contains only assembly metadata .</span></span> <span data-ttu-id="4ccbe-141">程序集的入口点是位于 `Main` 中的 `MainClientApp` 类中的 `Client.dll` 方法。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-141">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in `Client.dll`.</span></span>  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     <span data-ttu-id="4ccbe-142">可以使用 [MSIL 反汇编程序 (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 来检查程序集的内容，或者确定文件是程序集还是模块。</span><span class="sxs-lookup"><span data-stu-id="4ccbe-142">You can use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ccbe-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ccbe-143">See Also</span></span>  
 <span data-ttu-id="4ccbe-144">[创建程序集](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="4ccbe-144">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="4ccbe-145">[如何：查看程序集内容](../../../docs/framework/app-domains/how-to-view-assembly-contents.md) </span><span class="sxs-lookup"><span data-stu-id="4ccbe-145">[How to: View Assembly Contents](../../../docs/framework/app-domains/how-to-view-assembly-contents.md) </span></span>  
 <span data-ttu-id="4ccbe-146">[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="4ccbe-146">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 [<span data-ttu-id="4ccbe-147">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="4ccbe-147">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)

