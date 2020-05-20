---
ms.openlocfilehash: 7f528510e4158dad71280a7b1f269a231b8c60f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116329"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Microsoft.VisualBasic.Devices 命名空间中的类型不可用

<xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 命名空间中的类型不可用。

#### <a name="version-introduced"></a>引入的版本

.NET Core 3.0 预览版 8

#### <a name="change-description"></a>更改描述

<xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。 自 NET Core 3.0 预览版 9 起，它们不再可用。

已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。

#### <a name="recommended-action"></a>建议操作

如果你的代码依赖于对 <xref:Microsoft.VisualBasic.Devices> 类型及其成员的使用，可使用 .NET 类库中的相应类型或成员。 例如，<xref:System.DateTime?displayProperty=nameWithType> 和 <xref:System.Environment?displayProperty=nameWithType> 类型提供对 <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> 类等效的功能，<xref:System.IO.Ports?displayProperty=nameWithType> 命名空间中的类型可提供对 <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> 类等效的功能。

#### <a name="category"></a>类别

Visual Basic

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
