---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116363"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Microsoft.VisualBasic.MyServices 命名空间中的类型不可用

<xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 命名空间中的类型不可用。

#### <a name="version-introduced"></a>引入的版本

.NET Core 3.0 预览版 8

#### <a name="change-description"></a>更改描述

<xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。 自 NET Core 3.0 预览版 9 起，它们不再可用。

已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。

#### <a name="recommended-action"></a>建议操作

如果你的代码依赖于对 Microsoft.VisualBasic.MyServices 类型及其成员的使用，可使用 .NET 类库中的相应类型和成员  。 下面是 Microsoft.VisualBasic.MyServices 到其等效 .NET 类库类型的映射  ：

|Microsoft.VisualBasic.MyServices 类型|.NET 类库类型|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType> 用于 WPF 应用程序，<xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> 用于 Windows 窗体应用程序|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<xref:System.IO> 命名空间中的类型|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<xref:Microsoft.Win32> 命名空间中与注册表相关的类型|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>类别

Visual Basic

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
