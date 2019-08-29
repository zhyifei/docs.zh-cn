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
ms.openlocfilehash: 719ca45403ea56a655f06dbfea7c0fb7e32b34f7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046426"
---
# <a name="building-from-the-command-line-visual-basic"></a>从命令行生成 (Visual Basic)

Visual Basic 项目由一个或多个单独的源文件组成。 在此过程中, 将这些文件合并到一个包中, 这是一个可作为应用程序运行的单个可执行文件。

Visual Basic 提供了一个命令行编译器, 作为从 Visual Studio 集成开发环境 (IDE) 中编译程序的替代方法。 命令行编译器适用于不需要 IDE 中的整套功能的情况, 例如, 在系统内存或存储空间有限的计算机上使用或写入。

若要从 Visual Studio IDE 中编译源文件, 请从 "**生成**" 菜单中选择 "**生成**" 命令。

> [!TIP]
> 使用 Visual Studio IDE 生成项目文件时, 可以在 "输出" 窗口中显示相关联的**vbc**命令及其开关的相关信息。 若要显示此信息, 请打开 "[选项" 对话框、项目和解决方案、生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), 然后将 " **MSBuild 项目生成输出详细**级别" 设置为 "**正常**" 或更高级别的详细级别。 有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)。

您可以使用 MSBuild 在命令提示符下编译项目 (. .vbproj) 文件。 有关详细信息, 请参阅[命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)和[演练:使用 MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild)。

## <a name="in-this-section"></a>本节内容

[如何：调用命令行编译器](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) \
描述如何在 MS-DOS 提示符下或从特定子目录调用命令行编译器。

[示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) \
提供可为自己使用而修改的示例命令行列表。

## <a name="related-sections"></a>相关章节

[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) \
提供按字母顺序或目的排序的编译器选项列表。

[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) \
描述如何编译代码的特定部分。

[在 Visual Studio 中生成和清理项目和解决方案](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \
描述如何组织将包含在不同的生成中的内容, 选择 "项目属性", 并确保项目按正确的顺序生成。
