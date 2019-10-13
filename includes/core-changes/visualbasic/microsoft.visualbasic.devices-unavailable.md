---
ms.openlocfilehash: dae4afa92b8833f326b4eacd00b36bb3e1199cc1
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237292"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Microsoft.VisualBasic.Devices 命名空间中的类型不可用

<xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 命名空间中的类型不可用。

#### <a name="version-introduced"></a>引入的版本

.NET Core 3.0 预览版 8

#### <a name="change-description"></a>更改描述

<xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。 自 NET Core 3.0 预览版 9 起，它们不再可用。

已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。
 
#### <a name="recommended-action"></a>建议的操作

如果你的代码依赖于对 <xref:Microsoft.VisualBasic.Devices> 类型及其成员的使用，可使用 .NET 类库中的相应类型或成员。 例如，<xref:System.DateTime?displayProperty=nameWithType> 和 <xref:System.Environment?displayProperty=nameWithType> 类型提供对 <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> 类等效的功能，<xref:System.IO.Ports?displayProperty=nameWithType> 命名空间中的类型可提供对 <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> 类等效的功能。

#### <a name="category"></a>类别

Visual Basic

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

