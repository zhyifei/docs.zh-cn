---
title: 从命令行生成
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
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344795"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="0c0ce-102">从命令行生成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c0ce-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="0c0ce-103">Visual Basic 项目由一个或多个单独的源文件组成。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="0c0ce-104">在此过程中，将这些文件合并到一个包中，这是一个可作为应用程序运行的单个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="0c0ce-105">Visual Basic 提供了一个命令行编译器，作为从 Visual Studio 集成开发环境（IDE）中编译程序的替代方法。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="0c0ce-106">命令行编译器适用于不需要 IDE 中的整套功能的情况，例如，在系统内存或存储空间有限的计算机上使用或写入。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="0c0ce-107">若要从 Visual Studio IDE 中编译源文件，请从 "**生成**" 菜单中选择 "**生成**" 命令。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="0c0ce-108">使用 Visual Studio IDE 生成项目文件时，可以在 "输出" 窗口中显示相关联的**vbc**命令及其开关的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="0c0ce-109">若要显示此信息，请打开 "[选项" 对话框、项目和解决方案、生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后将 " **MSBuild 项目生成输出详细**级别" 设置为 "**正常**" 或更高级别的详细级别。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="0c0ce-110">有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="0c0ce-111">您可以使用 MSBuild 在命令提示符下编译项目（. .vbproj）文件。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="0c0ce-112">有关详细信息，请参阅[命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)和[演练：使用 MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild)。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0c0ce-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="0c0ce-113">In This Section</span></span>

<span data-ttu-id="0c0ce-114">[如何：调用命令行编译器](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="0c0ce-114">[How to: Invoke the Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="0c0ce-115">描述如何在 MS-DOS 提示符下或从特定子目录调用命令行编译器。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="0c0ce-116">[示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="0c0ce-116">[Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="0c0ce-117">提供可为自己使用而修改的示例命令行列表。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0c0ce-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="0c0ce-118">Related Sections</span></span>

<span data-ttu-id="0c0ce-119">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c0ce-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>\
<span data-ttu-id="0c0ce-120">提供按字母顺序或目的排序的编译器选项列表。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="0c0ce-121">[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="0c0ce-121">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="0c0ce-122">描述如何编译代码的特定部分。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="0c0ce-123">[在 Visual Studio 中生成和清理项目和解决方案](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="0c0ce-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="0c0ce-124">描述如何组织将包含在不同的生成中的内容，选择 "项目属性"，并确保项目按正确的顺序生成。</span><span class="sxs-lookup"><span data-stu-id="0c0ce-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
