---
title: 从命令行生成 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 89bcd6e0e7c1cc867bf853dc9bbe96628942ace2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866979"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="89359-102">从命令行生成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89359-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="89359-103">Visual Basic 项目由一个或多个单独的源代码文件组成。</span><span class="sxs-lookup"><span data-stu-id="89359-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="89359-104">在名为编译过程中，这些文件被集中到一个包，可以为应用程序运行的单个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="89359-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 <span data-ttu-id="89359-105">Visual Basic 提供命令行编译器作为从 Visual Studio 集成的开发环境 (IDE) 中编译程序的替代方法。</span><span class="sxs-lookup"><span data-stu-id="89359-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="89359-106">命令行编译器专为不需要完整的 IDE 中的功能集的情况下，例如，当您是使用或编写具有有限的系统内存或存储空间的计算机。</span><span class="sxs-lookup"><span data-stu-id="89359-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
  <span data-ttu-id="89359-107">若要编译源文件从 Visual Studio IDE 中的，选择**构建**命令**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="89359-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="89359-108">通过使用 Visual Studio IDE 生成项目文件时，可以显示有关关联的信息**vbc**命令和输出窗口中的其开关。</span><span class="sxs-lookup"><span data-stu-id="89359-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="89359-109">若要显示此信息，请打开[选项对话框、 项目和解决方案、 生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后设置**MSBuild 项目生成输出详细级别**到**正常**或更高级别的详细级别。</span><span class="sxs-lookup"><span data-stu-id="89359-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="89359-110">有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)。</span><span class="sxs-lookup"><span data-stu-id="89359-110">For more information, see [How to: View, Save, and Configure Build Log Files](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="89359-111">可以通过使用 MSBuild 编译在命令提示符下的项目 (.vbproj) 文件。</span><span class="sxs-lookup"><span data-stu-id="89359-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="89359-112">有关详细信息，请参阅[命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)并[演练： 使用 MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild)。</span><span class="sxs-lookup"><span data-stu-id="89359-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89359-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="89359-113">In This Section</span></span>  
 [<span data-ttu-id="89359-114">如何：调用命令行编译器</span><span class="sxs-lookup"><span data-stu-id="89359-114">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="89359-115">介绍如何调用命令行编译器在 MS-DOS 提示符处或从特定的子目录。</span><span class="sxs-lookup"><span data-stu-id="89359-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="89359-116">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="89359-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="89359-117">提供了一系列可以修改供自己使用的示例命令行。</span><span class="sxs-lookup"><span data-stu-id="89359-117">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="89359-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="89359-118">Related Sections</span></span>  
 [<span data-ttu-id="89359-119">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="89359-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="89359-120">提供编译器选项，按字母顺序或按目的组织的列表。</span><span class="sxs-lookup"><span data-stu-id="89359-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="89359-121">条件编译</span><span class="sxs-lookup"><span data-stu-id="89359-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="89359-122">描述如何编译代码的特定部分。</span><span class="sxs-lookup"><span data-stu-id="89359-122">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="89359-123">在 Visual Studio 中生成和清理项目和解决方案</span><span class="sxs-lookup"><span data-stu-id="89359-123">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="89359-124">说明如何组织什么将包含在不同版本中，选择项目属性中，并确保以正确的顺序生成项目。</span><span class="sxs-lookup"><span data-stu-id="89359-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
