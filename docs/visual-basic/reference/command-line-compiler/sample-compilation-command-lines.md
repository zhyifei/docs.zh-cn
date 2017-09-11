---
title: "示例编译命令行 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e58006c05f498ec1a9dbf5194fbc9bcdd281ab63
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="ca595-102">示例编译命令行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca595-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="ca595-103">作为编译的替代方法[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]程序从[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]，您可以从命令行以生成可执行文件 (.exe) 文件或动态链接库 (.dll) 文件进行编译。</span><span class="sxs-lookup"><span data-stu-id="ca595-103">As an alternative to compiling [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs from within [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="ca595-104">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]命令行编译器支持一组完整的控制输入和输出文件、 程序集，以及调试的选项和预处理器选项。</span><span class="sxs-lookup"><span data-stu-id="ca595-104">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="ca595-105">每个选项可在两个可互换的窗体中︰`-``option`和`/``option`。</span><span class="sxs-lookup"><span data-stu-id="ca595-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="ca595-106">本文档仅显示`/``option`窗体。</span><span class="sxs-lookup"><span data-stu-id="ca595-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="ca595-107">下表列出了一些示例命令行，您可以修改供自己使用。</span><span class="sxs-lookup"><span data-stu-id="ca595-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="ca595-108">到</span><span class="sxs-lookup"><span data-stu-id="ca595-108">To</span></span>|<span data-ttu-id="ca595-109">使用</span><span class="sxs-lookup"><span data-stu-id="ca595-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="ca595-110">编译 File.vb 并创建 File.exe</span><span class="sxs-lookup"><span data-stu-id="ca595-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="ca595-111">编译 File.vb 并创建 File.dll</span><span class="sxs-lookup"><span data-stu-id="ca595-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="ca595-112">编译 File.vb 并创建 My.exe</span><span class="sxs-lookup"><span data-stu-id="ca595-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="ca595-113">将所有编译[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]上文件在当前目录中，进行了优化和`DEBUG`符号定义，从而生成 File2.exe</span><span class="sxs-lookup"><span data-stu-id="ca595-113">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="ca595-114">将所有编译[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]文件在当前目录中，不显示徽标或警告的情况下生成 File2.dll 的调试版本</span><span class="sxs-lookup"><span data-stu-id="ca595-114">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="ca595-115">将所有编译[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Something.dll 到当前目录中的文件</span><span class="sxs-lookup"><span data-stu-id="ca595-115">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="ca595-116">当从命令行编译时，必须显式引用 Microsoft[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]通过运行时库`/reference`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="ca595-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ca595-117">通过使用 Visual Studio IDE 生成项目时，可以显示有关关联信息**vbc**命令，并在输出窗口中与之编译器选项。</span><span class="sxs-lookup"><span data-stu-id="ca595-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="ca595-118">若要显示此信息，请打开[选项对话框、 项目和解决方案、 生成和运行](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后设置**MSBuild 项目生成输出详细程度**到**正常**或更高版本的详细程度级别。</span><span class="sxs-lookup"><span data-stu-id="ca595-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="ca595-119">有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)。</span><span class="sxs-lookup"><span data-stu-id="ca595-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca595-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca595-120">See Also</span></span>  
 <span data-ttu-id="ca595-121">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca595-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ca595-122"> [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="ca595-122"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
