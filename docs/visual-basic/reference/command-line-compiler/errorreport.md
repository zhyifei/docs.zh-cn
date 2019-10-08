---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: c8e193a8cb4d4dbc7515c32139bad9dce8b48ed7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005618"
---
# <a name="-errorreport"></a>-errorreport

指定 Visual Basic 编译器如何报告内部编译器错误。

## <a name="syntax"></a>语法

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>备注

使用此选项可以方便地向 Microsoft 报告 Visual Basic 内部编译器错误（ICE）到 Visual Basic 团队。 默认情况下，编译器不向 Microsoft 发送任何信息。 但是，如果遇到内部编译器错误，则可以使用此选项向 Microsoft 报告错误。 该信息将帮助 Microsoft 工程师找出原因，并帮助改进 Visual Basic 的下一版本。

用户发送报表的能力取决于计算机和用户策略的权限。

下表总结了 `-errorreport` 选项的影响。

|选项|行为|
|---|---|
|`prompt`|如果发生内部编译器错误，则会出现一个对话框，以便您可以查看编译器收集的确切数据。 您可以确定错误报告中是否存在任何敏感信息，并决定是否将其发送给 Microsoft。 如果你决定发送它，并且计算机和用户策略设置允许它，则编译器会将数据发送给 Microsoft。|
|`queue`|将错误报告排入队列。 当你以管理员权限登录时，你可以报告自上次登录后发生的任何失败（系统将不会提示你每三天发送一次失败的报告）。 这是未指定 `-errorreport` 选项时的默认行为。|
|`send`|如果发生内部编译器错误，并且计算机和用户策略设置允许，则编译器会将数据发送给 Microsoft。<br /><br /> 如果[Windows 错误报告](/windows/desktop/wer/windows-error-reporting)系统设置启用了报告，则选项 `-errorreport:send` 会尝试自动向 Microsoft 发送错误信息。 |
|`none`|如果发生内部编译器错误，则不会将其收集或发送给 Microsoft。|

编译器将在出现错误时发送包括堆栈的数据，这通常包括一些源代码。 如果 `-errorreport` 与[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项一起使用，则将发送整个源文件。

此选项最适合用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它允许 Microsoft 工程师更轻松地重现错误。

> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-errorreport` 选项;仅当从命令行进行编译时，它才可用。

## <a name="example"></a>示例

下面的代码尝试编译 `T2.vb`，如果编译器遇到内部编译器错误，则会提示你将错误报告发送给 Microsoft。

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
