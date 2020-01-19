---
ms.openlocfilehash: d8cc506d60f3c24087ebde8ead345656fea0f484
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116335"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Microsoft.VisualBasic.ApplicationServices 命名空间中的类型不可用

<xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 命名空间中的类型不可用。

#### <a name="version-introduced"></a>引入的版本

.NET Core 3.0 预览版 8

#### <a name="change-description"></a>更改描述

<xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 中的类型之前在某些 .NET Core 3.0 预览版本中可用。 自 NET Core 3.0 预览版 9 起，它们不再可用。

已删除这些类型，以避免在后续版本中出现不必要的程序集依赖项或中断性变更。

#### <a name="recommended-action"></a>建议操作

如果你的代码依赖于对 <xref:Microsoft.VisualBasic.ApplicationServices> 类型及其成员的使用，可使用 .NET 类库中的相应类型或成员。 例如，一些 <xref:System.Environment?displayProperty=nameWithType> 和 <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> 成员对 <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> 类的属性提供等效功能。

#### <a name="category"></a>类别

Visual Basic

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
