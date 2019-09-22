---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117118"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine 已过时

<xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 常数在 .NET Framework 中被标记为[已过时](xref:System.ObsoleteAttribute)，但之前在 .net Core 3.0 库中缺少该属性。

#### <a name="version-introduced"></a>引入的版本

.NET Core 3.0 预览版 8

#### <a name="details"></a>详细信息

从 .NET Core 3.0 预览版 8 开始，已将[已过时](xref:System.ObsoleteAttribute)属性应用于 <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> 常数，使其符合 .NET Framework 中的 `vbNewLine`。 使用 `vbNewLine` 常量会生成编译器警告。 

在早期版本的 .Net Core 中，`vbNewLine` 不会生成编译器警告。

#### <a name="recommended-action"></a>建议的操作

`vbNewLine` 的[已过时](xref:System.ObsoleteAttribute)属性消息包含以下建议：

> 对于回车符和换行符，请使用 [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf)。 对于当前平台的新行，请使用 <xref:System.Environment.NewLine?displayProperty=nameWithType>。

#### <a name="category"></a>类别

Visual Basic

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

