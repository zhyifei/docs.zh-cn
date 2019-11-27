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
# <a name="sample-compilation-command-lines-visual-basic"></a>示例编译命令行（Visual Basic）

作为从 Visual Studio 中编译 Visual Basic 程序的替代方法，您可以从命令行进行编译，以生成可执行（.exe）文件或动态链接库（.dll）文件。

Visual Basic 命令行编译器支持一组完整的选项，这些选项控制输入和输出文件、程序集以及调试和预处理器选项。 每个选项都以两种可互换形式提供： `-option` 和 `/option`。 此文档仅显示 `-option` 窗体。

下表列出了可为自己使用而修改的一些示例命令行。

|至|使用|
|--------|---------|
|编译文件 .vb 并创建文件 .exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|编译文件 .vb 并创建文件 .dll|`vbc -target:library File.vb`|
|编译文件 .vb 并创建 .exe|`vbc -out:My.exe File.vb`|
|编译文件 .vb 并创建名为 File .dll 的库和引用程序集|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|编译当前目录中的所有 Visual Basic 文件，并定义了优化并定义了 `DEBUG` 符号，从而生成 File2|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|编译当前目录中的所有 Visual Basic 文件，生成 File2 的调试版本而不显示徽标或警告|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|将当前目录中的所有 Visual Basic 文件编译为某些内容 .dll|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> 使用 Visual Studio IDE 生成项目时，可以在 "输出" 窗口中显示相关联的**vbc**命令及其编译器选项的相关信息。 若要显示此信息，请打开 "[选项" 对话框、项目和解决方案、生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后将 " **MSBuild 项目生成输出详细**级别" 设置为 "**正常**" 或更高级别的详细级别。

## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
