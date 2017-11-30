---
title: "从命令行生成 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d982506af2c4f01e80ae5b3862fcbcfff2aa9d99
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="75a03-102">从命令行生成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75a03-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="75a03-103">A[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]项目由一个或多个单独的源文件组成。</span><span class="sxs-lookup"><span data-stu-id="75a03-103">A [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project is made up of one or more separate source files.</span></span> <span data-ttu-id="75a03-104">在称为编译过程中，这些文件被集中到一个包中，可以为应用程序运行的单个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="75a03-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="75a03-105">作为编译来自程序的替代方法提供命令行编译器[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]集成的开发环境 (IDE)。</span><span class="sxs-lookup"><span data-stu-id="75a03-105"> provides a command-line compiler as an alternative to compiling programs from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="75a03-106">命令行编译器设计为不需要完整的 IDE 中的功能集情况-例如，当你正在使用或者编写的有限的系统内存或存储空间使用的计算机。</span><span class="sxs-lookup"><span data-stu-id="75a03-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
 <span data-ttu-id="75a03-107">在从命令行编译时，必须显式引用 Microsoft[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]通过运行时库`/reference`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="75a03-107">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
 <span data-ttu-id="75a03-108">若要编译中的源文件[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]IDE 中，选择**生成**命令**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="75a03-108">To compile source files from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="75a03-109">通过使用 Visual Studio IDE 生成项目文件时，你可以显示有关信息关联**vbc**命令，并在输出窗口中的开关。</span><span class="sxs-lookup"><span data-stu-id="75a03-109">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="75a03-110">若要显示此信息，请打开[选项对话框、 项目和解决方案、 生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后设置**MSBuild 项目生成输出详细级别**到**正常**或更高级别的详细级别。</span><span class="sxs-lookup"><span data-stu-id="75a03-110">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="75a03-111">有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)。</span><span class="sxs-lookup"><span data-stu-id="75a03-111">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="75a03-112">可以使用 MSBuild 来编译在命令提示符下的项目 (.vbproj) 文件。</span><span class="sxs-lookup"><span data-stu-id="75a03-112">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="75a03-113">有关详细信息，请参阅[命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)和[演练： 使用 MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild)。</span><span class="sxs-lookup"><span data-stu-id="75a03-113">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75a03-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="75a03-114">In This Section</span></span>  
 [<span data-ttu-id="75a03-115">如何：调用命令行编译器</span><span class="sxs-lookup"><span data-stu-id="75a03-115">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="75a03-116">介绍如何调用命令行编译器 MS-DOS 提示符处或从特定的子目录。</span><span class="sxs-lookup"><span data-stu-id="75a03-116">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="75a03-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="75a03-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="75a03-118">提供的可以修改供自己使用的示例命令行的列表。</span><span class="sxs-lookup"><span data-stu-id="75a03-118">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="75a03-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="75a03-119">Related Sections</span></span>  
 [<span data-ttu-id="75a03-120">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="75a03-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="75a03-121">提供的编译器选项，按字母顺序还是按目的组织的列表。</span><span class="sxs-lookup"><span data-stu-id="75a03-121">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="75a03-122">条件编译</span><span class="sxs-lookup"><span data-stu-id="75a03-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="75a03-123">描述如何编译代码的特定部分。</span><span class="sxs-lookup"><span data-stu-id="75a03-123">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="75a03-124">在 Visual Studio 中生成和清理项目和解决方案</span><span class="sxs-lookup"><span data-stu-id="75a03-124">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="75a03-125">描述如何组织什么将包含在不同的版本，请选择项目属性中，并确保按正确的顺序生成项目。</span><span class="sxs-lookup"><span data-stu-id="75a03-125">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
