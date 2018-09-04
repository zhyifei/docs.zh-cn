---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509668"
---
# <a name="-errorreport"></a>-errorreport

指定 Visual Basic 编译器应报告内部编译器错误的方式。

## <a name="syntax"></a>语法

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>备注

此选项提供了 Visual Basic 团队在 Microsoft Visual Basic 内部编译器错误 (ICE) 报告的简便方法。 默认情况下，编译器会向 Microsoft 发送任何信息。 但是，如果执行操作时遇到内部编译器错误，此选项允许你向 Microsoft 报告错误。 该信息将帮助 Microsoft 工程师确定原因以及可帮助提高下一版本的 Visual Basic。

发送报表的用户的能力取决于计算机和用户策略权限。

下表总结了的效果`-errorreport`选项。

|选项|行为|
|---|---|
|`prompt`|如果发生内部编译器错误，弹出对话框，以便您可以查看编译器收集的确切数据。 可以判断是否有错误报告中的任何敏感信息并决定将其发送给 Microsoft。 如果你决定发送它，并且计算机和用户策略设置允许它，编译器会将数据发送给 Microsoft。|
|`queue`|将错误报告排入队列。 当使用管理员权限登录时，可以报告自上次登录以来的任何失败 （将不会提示您发送一次每隔三天的故障报告）。 这是默认行为时`-errorreport`未指定选项。|
|`send`|发生内部编译器错误，并将计算机和用户策略设置允许它，编译器会向 Microsoft 发送数据。<br /><br /> 选项`-errorreport:send`尝试自动向 Microsoft 发送错误的信息，如果通过启用报告[Windows 错误报告](/windows/desktop/wer/windows-error-reporting)系统设置。 |
|`none`|如果发生内部编译器错误，它不会收集或发送给 Microsoft。|

编译器将发送包含一个错误，它通常包含某些源代码时堆栈的数据。 如果`-errorreport`用于[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，则发送整个源文件。

此选项最适合用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它可让 Microsoft 工程师更轻松地重现错误。

> [!NOTE]
> `-errorreport`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。

## <a name="example"></a>示例

下面的代码尝试编译`T2.vb`，如果编译器遇到内部编译器错误时，它会提示你向 Microsoft 发送错误报告。

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
