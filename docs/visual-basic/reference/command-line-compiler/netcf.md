---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 3df7e622f97a5a1291736180e3964b1b3deaea2f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005446"
---
# <a name="-netcf"></a>-netcf

设置编译器以面向 .NET Compact Framework。

## <a name="syntax"></a>语法

```console
-netcf
```

## <a name="remarks"></a>备注

`-netcf` 选项导致 Visual Basic 编译器以 .NET Compact Framework 而不是完整 .NET Framework 为目标。 仅在完整 .NET Framework 中显示的语言功能处于禁用状态。

`-netcf` 选项设计为与[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)一起使用。 `-netcf` 禁用的语言功能与 `-sdkpath`面向的文件中不存在相同的语言功能。

> [!NOTE]
> `-netcf` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。 `-netcf` 选项是在加载 Visual Basic 设备项目时设置的。

`-netcf` 选项更改以下语言功能：

- 禁用了[End \<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)关键字，该关键字终止程序的执行。 下面的程序在编译和运行时不 `-netcf`，但在编译时与 `-netcf`发生了故障。

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- 所有窗体中的后期绑定都处于禁用状态。 如果遇到可识别的后期绑定方案，则会生成编译时错误。 下面的程序在编译和运行时不 `-netcf`，但在编译时与 `-netcf`发生了故障。

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)、 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)和[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修饰符已禁用。 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)语句的语法还会修改为 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`。 下面的代码演示了对编译 `-netcf` 的影响。

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- 使用从 Visual Basic 中删除的 Visual Basic 6.0 关键字会在使用 `-netcf` 时生成不同的错误。 这会影响以下关键字的错误消息：

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>示例

下面的代码使用 C 驱动器上 .NET Compact Framework 的默认安装目录中的 mscorlib.dll 和 .NET Compact Framework 版本，将 `Myfile.vb` 编译为。 通常，您将使用最新版本的 .NET Compact Framework。

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
