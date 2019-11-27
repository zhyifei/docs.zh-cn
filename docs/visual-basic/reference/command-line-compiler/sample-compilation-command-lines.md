---
title: 示例编译命令行
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350845"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="973a1-102">示例编译命令行（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="973a1-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="973a1-103">作为从 Visual Studio 中编译 Visual Basic 程序的替代方法，您可以从命令行进行编译，以生成可执行（.exe）文件或动态链接库（.dll）文件。</span><span class="sxs-lookup"><span data-stu-id="973a1-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="973a1-104">Visual Basic 命令行编译器支持一组完整的选项，这些选项控制输入和输出文件、程序集以及调试和预处理器选项。</span><span class="sxs-lookup"><span data-stu-id="973a1-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="973a1-105">每个选项都以两种可互换形式提供： `-option` 和 `/option`。</span><span class="sxs-lookup"><span data-stu-id="973a1-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="973a1-106">此文档仅显示 `-option` 窗体。</span><span class="sxs-lookup"><span data-stu-id="973a1-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="973a1-107">下表列出了可为自己使用而修改的一些示例命令行。</span><span class="sxs-lookup"><span data-stu-id="973a1-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="973a1-108">至</span><span class="sxs-lookup"><span data-stu-id="973a1-108">To</span></span>|<span data-ttu-id="973a1-109">使用</span><span class="sxs-lookup"><span data-stu-id="973a1-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="973a1-110">编译文件 .vb 并创建文件 .exe</span><span class="sxs-lookup"><span data-stu-id="973a1-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="973a1-111">编译文件 .vb 并创建文件 .dll</span><span class="sxs-lookup"><span data-stu-id="973a1-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="973a1-112">编译文件 .vb 并创建 .exe</span><span class="sxs-lookup"><span data-stu-id="973a1-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="973a1-113">编译文件 .vb 并创建名为 File .dll 的库和引用程序集</span><span class="sxs-lookup"><span data-stu-id="973a1-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="973a1-114">编译当前目录中的所有 Visual Basic 文件，并定义了优化并定义了 `DEBUG` 符号，从而生成 File2</span><span class="sxs-lookup"><span data-stu-id="973a1-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="973a1-115">编译当前目录中的所有 Visual Basic 文件，生成 File2 的调试版本而不显示徽标或警告</span><span class="sxs-lookup"><span data-stu-id="973a1-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="973a1-116">将当前目录中的所有 Visual Basic 文件编译为某些内容 .dll</span><span class="sxs-lookup"><span data-stu-id="973a1-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="973a1-117">使用 Visual Studio IDE 生成项目时，可以在 "输出" 窗口中显示相关联的**vbc**命令及其编译器选项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="973a1-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="973a1-118">若要显示此信息，请打开 "[选项" 对话框、项目和解决方案、生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后将 " **MSBuild 项目生成输出详细**级别" 设置为 "**正常**" 或更高级别的详细级别。</span><span class="sxs-lookup"><span data-stu-id="973a1-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="973a1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="973a1-119">See also</span></span>

- [<span data-ttu-id="973a1-120">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="973a1-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="973a1-121">条件编译</span><span class="sxs-lookup"><span data-stu-id="973a1-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
