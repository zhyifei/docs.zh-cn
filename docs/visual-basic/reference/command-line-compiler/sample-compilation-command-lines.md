---
title: "示例编译命令行 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e168d40a22ca3737bee18f966df95988a2736a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="8255f-102">示例编译命令行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8255f-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="8255f-103">作为编译的替代方法[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]内程序[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]，你可以从命令行以生成可执行文件 (.exe) 文件或动态链接库 (.dll) 文件进行编译。</span><span class="sxs-lookup"><span data-stu-id="8255f-103">As an alternative to compiling [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="8255f-104">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]命令行编译器支持一组完整的控制输入和输出文件、 程序集，以及调试的选项和预处理器的选项。</span><span class="sxs-lookup"><span data-stu-id="8255f-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="8255f-105">每个选项可在两个可互换的窗体中：`-``option`和`/``option`。</span><span class="sxs-lookup"><span data-stu-id="8255f-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="8255f-106">本文档只会显示`/``option`窗体。</span><span class="sxs-lookup"><span data-stu-id="8255f-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="8255f-107">下表列出了你可以修改供自己使用的一些示例命令行。</span><span class="sxs-lookup"><span data-stu-id="8255f-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="8255f-108">到</span><span class="sxs-lookup"><span data-stu-id="8255f-108">To</span></span>|<span data-ttu-id="8255f-109">使用</span><span class="sxs-lookup"><span data-stu-id="8255f-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="8255f-110">编译 File.vb 并创建 File.exe</span><span class="sxs-lookup"><span data-stu-id="8255f-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="8255f-111">编译 File.vb 并创建 File.dll</span><span class="sxs-lookup"><span data-stu-id="8255f-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="8255f-112">编译 File.vb 并创建 My.exe</span><span class="sxs-lookup"><span data-stu-id="8255f-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="8255f-113">编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]在上文件在当前目录中，通过使用优化和`DEBUG`定义，从而生成 File2.exe 的符号</span><span class="sxs-lookup"><span data-stu-id="8255f-113">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="8255f-114">编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]在当前目录中，而不显示的徽标或警告生成 File2.dll 的调试版本的文件</span><span class="sxs-lookup"><span data-stu-id="8255f-114">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="8255f-115">编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Something.dll 到当前目录中的文件</span><span class="sxs-lookup"><span data-stu-id="8255f-115">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="8255f-116">在从命令行编译时，必须显式引用 Microsoft[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]通过运行时库`/reference`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="8255f-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="8255f-117">通过使用 Visual Studio IDE 生成项目时，你可以显示有关信息关联**vbc**命令使用其在输出窗口中的编译器选项。</span><span class="sxs-lookup"><span data-stu-id="8255f-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="8255f-118">若要显示此信息，请打开[选项对话框、 项目和解决方案、 生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后设置**MSBuild 项目生成输出详细级别**到**正常**或更高级别的详细级别。</span><span class="sxs-lookup"><span data-stu-id="8255f-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="8255f-119">有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)。</span><span class="sxs-lookup"><span data-stu-id="8255f-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8255f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8255f-120">See Also</span></span>  
 [<span data-ttu-id="8255f-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="8255f-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8255f-122">条件编译</span><span class="sxs-lookup"><span data-stu-id="8255f-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
