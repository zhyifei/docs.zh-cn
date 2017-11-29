---
title: "令映像更易于调试"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 46a9c11f3545e5d2b9f91572a87ee2614810e4d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="making-an-image-easier-to-debug"></a><span data-ttu-id="531cf-102">令映像更易于调试</span><span class="sxs-lookup"><span data-stu-id="531cf-102">Making an Image Easier to Debug</span></span>
<span data-ttu-id="531cf-103">编译非托管代码时，可以通过设置 IDE 开关或命令线选项来配置可执行映像进行调试。</span><span class="sxs-lookup"><span data-stu-id="531cf-103">When compiling unmanaged code, you can configure an executable image for debugging by setting IDE switches or command-line options.</span></span> <span data-ttu-id="531cf-104">例如，可以使用 Visual C++ 中的 /Zi 命令行选项，使其发出调试符号文件（文件扩展名为 .pdb）。</span><span class="sxs-lookup"><span data-stu-id="531cf-104">For example, you can use the /**Zi** command-line option in Visual C++ to ask it to emit debug symbol files (file extension .pdb).</span></span> <span data-ttu-id="531cf-105">同样，/Od 命令行选项告知编译器禁用优化。</span><span class="sxs-lookup"><span data-stu-id="531cf-105">Similarly, the /**Od** command-line option tells the compiler to disable optimization.</span></span> <span data-ttu-id="531cf-106">所产生的代码运行速度更慢，但更易于调试，这很必要。</span><span class="sxs-lookup"><span data-stu-id="531cf-106">The resulting code runs more slowly, but is easier to debug, should this be necessary.</span></span>  
  
 <span data-ttu-id="531cf-107">编译 .NET Framework 托管代码时，Visual C ++、Visual Basic 和 C# 等编译器将它们的源程序编译成 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="531cf-107">When compiling .NET Framework managed code, compilers such as Visual C++, Visual Basic, and C# compile their source program into Microsoft Intermediate Language (MSIL).</span></span> <span data-ttu-id="531cf-108">随后，在执行前将 MSIL 实时编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="531cf-108">MSIL is subsequently JIT-compiled, just before execution, into native machine code.</span></span> <span data-ttu-id="531cf-109">与非托管代码一样，可以通过设置 IDE 开关或命令行选项来配置可执行映像进行调试。</span><span class="sxs-lookup"><span data-stu-id="531cf-109">As with unmanaged code, you can configure an executable image for debugging by setting IDE switches or command-line options.</span></span> <span data-ttu-id="531cf-110">此外，可采用大致相同的方式配置 JIT 编译进行调试。</span><span class="sxs-lookup"><span data-stu-id="531cf-110">In addition, you can configure the JIT compilation for debugging in much the same way.</span></span>  
  
 <span data-ttu-id="531cf-111">这种 JIT 配置具有两个方面：</span><span class="sxs-lookup"><span data-stu-id="531cf-111">This JIT configuration has two aspects:</span></span>  
  
-   <span data-ttu-id="531cf-112">可以请求 JIT 编译器生成跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="531cf-112">You can request the JIT-compiler to generate tracking information.</span></span> <span data-ttu-id="531cf-113">这使调试程序能将 MSIL 链与其机器码对应项相匹配，并跟踪存储本地变量和函数参数的位置。</span><span class="sxs-lookup"><span data-stu-id="531cf-113">This makes it possible for the debugger to match up a chain of MSIL with its machine code counterpart, and to track where local variables and function arguments are stored.</span></span>  <span data-ttu-id="531cf-114">在 .NET Framework 2.0 版中，JIT 编译器将始终生成跟踪信息，因此无需进行请求。</span><span class="sxs-lookup"><span data-stu-id="531cf-114">In the .NET Framework version 2.0, the JIT compiler will always generate tracking information, so there is no need to request it.</span></span>  
  
-   <span data-ttu-id="531cf-115">可以请求 JIT 编译器不优化生成的计算机代码。</span><span class="sxs-lookup"><span data-stu-id="531cf-115">You can request the JIT-compiler to not optimize the resulting machine code.</span></span>  
  
 <span data-ttu-id="531cf-116">通常，生成 MSIL 的编译器根据指定的 IDE 开关或命令行选项（例如 /Od）适当地设置这些 JIT 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="531cf-116">Normally, the compiler that generates the MSIL sets these JIT-compiler options appropriately, based upon the IDE switches or command-line options you specify, for example, /**Od**.</span></span>  
  
 <span data-ttu-id="531cf-117">某些情况下，可能需要更改 JIT 编译器的行为，使其生成的机器码更易于调试。</span><span class="sxs-lookup"><span data-stu-id="531cf-117">In some cases, you might want to change the behavior of the JIT compiler so that the machine code it generates is easier to debug.</span></span> <span data-ttu-id="531cf-118">例如，可能希望为零售版本或控制优化生成实时跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="531cf-118">For example, you might want to generate JIT tracking information for a retail build or control optimization.</span></span> <span data-ttu-id="531cf-119">可以使用初始化 (.ini) 文件来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="531cf-119">You can do so with an initialization (.ini) file.</span></span>  
  
 <span data-ttu-id="531cf-120">例如，如果要调试的程序集名为 MyApp.exe，则可在 MyApp.exe 所在的文件夹创建名为 MyApp.ini 的文本文件，其中包含以下三行：</span><span class="sxs-lookup"><span data-stu-id="531cf-120">For example, if the assembly you want to debug is called MyApp.exe, then you can create a text file named MyApp.ini, in the same folder as MyApp.exe, which contains these three lines:</span></span>  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 <span data-ttu-id="531cf-121">可将每个选项的值设置为 0 或 1，任何不存在选项默认为 0。</span><span class="sxs-lookup"><span data-stu-id="531cf-121">You can set the value of each option to 0 or 1, and any absent option defaults to 0.</span></span> <span data-ttu-id="531cf-122">将 `GenerateTrackingInfo` 设为 1、`AllowOptimize` 设为 0，这可提供最简单的调试。</span><span class="sxs-lookup"><span data-stu-id="531cf-122">Setting `GenerateTrackingInfo` to 1 and `AllowOptimize` to 0 provides the easiest debugging.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="531cf-123">在 .NET Framework 2.0 版中，无论 `GenerateTrackingInfo` 的值为多少，JIT 编译器始终生成跟踪信息；但是，`AllowOptimize` 值仍产生影响。</span><span class="sxs-lookup"><span data-stu-id="531cf-123">In the .NET Framework version 2.0, the JIT compiler always generates tracking information regardless of the value for `GenerateTrackingInfo`; however, the `AllowOptimize` value still has an effect.</span></span> <span data-ttu-id="531cf-124">如果使用 [Ngen.exe（本机映像生成器）](../../../docs/framework/tools/ngen-exe-native-image-generator.md)预编译本机映像而不进行优化，Ngen.exe 执行时 .ini 文件必须存在于 `AllowOptimize=0` 的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="531cf-124">When using the [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) to precompile the native image without optimization, the .ini file must be present in the target folder with `AllowOptimize=0` when Ngen.exe executes.</span></span> <span data-ttu-id="531cf-125">如果已经预编译程序集而不进行优化，则必须使用 NGen.exe /uninstall 选项删除预编译的代码，才能重新运行 Ngen.exe 将代码预编译为优化。</span><span class="sxs-lookup"><span data-stu-id="531cf-125">If you have precompiled an assembly without optimization, you must remove the precompiled code using the NGen.exe **/uninstall** option before rerunning Ngen.exe to precompile the code as optimized.</span></span> <span data-ttu-id="531cf-126">如果文件夹中不存在 .ini 文件，则默认 Ngen.exe 将代码预编译为优化。</span><span class="sxs-lookup"><span data-stu-id="531cf-126">If the .ini file is not present in the folder, by default Ngen.exe precompiles the code as optimized.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="531cf-127"><xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> 控制程序集的设置。</span><span class="sxs-lookup"><span data-stu-id="531cf-127">The <xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controls the settings for an assembly.</span></span> <span data-ttu-id="531cf-128">DebuggableAttribute 包括两个字段，用于记录 JIT 编译器是否应优化和/或生成跟踪信息的设置。</span><span class="sxs-lookup"><span data-stu-id="531cf-128">**DebuggableAttribute** includes two fields that record the settings for whether the JIT compiler should optimize, and/or generate tracking information.</span></span> <span data-ttu-id="531cf-129">在 .NET Framework 2.0 版本中，JIT 编译器将始终生成跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="531cf-129">In the .NET Framework version 2.0, the JIT compiler will always generate tracking information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="531cf-130">对于零售版本，编译器不设置任何 DebuggableAttribute。</span><span class="sxs-lookup"><span data-stu-id="531cf-130">For a retail build, compilers do not set any **DebuggableAttribute**.</span></span> <span data-ttu-id="531cf-131">JIT 编译器的默认行为是生成最高性能最难调试的机器码。</span><span class="sxs-lookup"><span data-stu-id="531cf-131">The JIT-compiler default behavior is to generate the highest performance, hardest to debug machine code.</span></span> <span data-ttu-id="531cf-132">启用实时跟踪会稍微降低性能，禁用优化会极大降低性能。</span><span class="sxs-lookup"><span data-stu-id="531cf-132">Enabling JIT tracking lowers performance a little, and disabling optimization lowers performance a lot.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="531cf-133">DebuggableAttribute 一次应用于整个程序集，而不是应用于程序集中的单个模块。</span><span class="sxs-lookup"><span data-stu-id="531cf-133">The **DebuggableAttribute** applies to a whole assembly at a time, not to individual modules within the assembly.</span></span> <span data-ttu-id="531cf-134">因此，开发工具必须将自定义属性附加到程序集元数据令牌，如果已经创建程序集，则附加到名为 System.Runtime.CompilerServices.AssemblyAttributesGoHere 的类。</span><span class="sxs-lookup"><span data-stu-id="531cf-134">Development tools must therefore attach custom attributes to the assembly metadata token, if an assembly has already been created, or to the class called **System.Runtime.CompilerServices.AssemblyAttributesGoHere**.</span></span> <span data-ttu-id="531cf-135">然后，ALink 工具将这些 DebuggableAttribute 属性从每个模块提升至它们将属于的程序集。</span><span class="sxs-lookup"><span data-stu-id="531cf-135">The ALink tool will then promote these **DebuggableAttribute** attributes from each module to the assembly they become a part of.</span></span> <span data-ttu-id="531cf-136">如果存在冲突，ALink 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="531cf-136">If there is a conflict, the ALink operation will fail.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="531cf-137">在 .NET Framework 1.0 版本中，当指定 /clr 和 /Zi 编译器选项时，Microsoft Visual C++ 编译器将添加 DebuggableAttribute。</span><span class="sxs-lookup"><span data-stu-id="531cf-137">In version 1.0 of the .NET Framework, the Microsoft Visual C++ compiler adds the **DebuggableAttribute** when the **/clr** and **/Zi** compiler options are specified.</span></span> <span data-ttu-id="531cf-138">在 .NET Framework 1.1 版本中，必须在代码中手动添加 DebugabbleAttribute，或者使用 /ASSEMBLYDEBUG 链接器选项。</span><span class="sxs-lookup"><span data-stu-id="531cf-138">In version 1.1 of the .NET Framework, you must either add the **DebugabbleAttribute** manually in your code or use the **/ASSEMBLYDEBUG** linker option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="531cf-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="531cf-139">See Also</span></span>  
 [<span data-ttu-id="531cf-140">调试、跟踪和分析</span><span class="sxs-lookup"><span data-stu-id="531cf-140">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)  
 [<span data-ttu-id="531cf-141">启用 JIT 附加调试</span><span class="sxs-lookup"><span data-stu-id="531cf-141">Enabling JIT-Attach Debugging</span></span>](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 [<span data-ttu-id="531cf-142">启用分析</span><span class="sxs-lookup"><span data-stu-id="531cf-142">Enabling Profiling</span></span>](http://msdn.microsoft.com/en-us/3b669676-f0e0-4ebf-8674-68986dd2020d)
