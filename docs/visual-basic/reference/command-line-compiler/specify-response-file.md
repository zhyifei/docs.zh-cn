---
title: '@（指定响应文件）'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: c578495bbba0efee79f02da284c7feffb8c12fab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348553"
---
# <a name="-specify-response-file-visual-basic"></a>@（指定响应文件）(Visual Basic)

指定包含要编译的编译器选项和源代码文件的文件。

## <a name="syntax"></a>语法

```console
@response_file
```

## <a name="arguments"></a>参数

`response_file`  
必需。 列出编译器选项或要编译的源代码文件的文件。 如果文件名包含空格，请将文件名用引号（""）引起来。

## <a name="remarks"></a>备注

编译器将处理在响应文件中指定的编译器选项和源代码文件，就好像已在命令行中指定了这些选项。

若要在编译中指定多个响应文件，请指定多个响应文件选项，如下所示。

```console
@file1.rsp @file2.rsp
```

在响应文件中，多个编译器选项和源代码文件可以出现在一行中。 单个编译器选项规范必须出现在一行中（不能跨多行）。 响应文件可以包含以 `#` 符号开头的注释。

可以将命令行上指定的选项与一个或多个响应文件中指定的选项组合在一起。 编译器在遇到命令选项时进行处理。 因此，命令行参数可以重写以前在响应文件中列出的选项。 相反，响应文件中的选项会替代前面的命令行或其他响应文件中列出的选项。

Visual Basic 提供了 Vbc 文件，该文件与 Vbc 文件位于同一目录中。 默认情况下，将包含 Vbc 文件，除非使用 `-noconfig` 选项。 有关详细信息，请参阅[-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)。

> [!NOTE]
> `@` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。

## <a name="example"></a>示例

以下行来自示例响应文件。

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a>示例

下面的示例演示如何将 `@` 选项与名为 `File1.rsp`的响应文件一起使用。

```console
vbc @file1.rsp
```

## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
