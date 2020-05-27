---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721745"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>更改访问 AccessibleObject.RuntimeIDFirstItem 的权限

从 .NET Core 3.0 RC1 开始，`AccessibleObject.RuntimeIDFirstItem` 的可访问性已从 `protected` 更改为 `internal`。

#### <a name="change-description"></a>更改描述

从 .NET Core 3.0 预览版 4 开始，`AccessibleObject.RuntimeIDFirstItem` 字段为 `protected`。 从 .NET Core 3.0 RC1 开始，它已从 `protected` 更改为 `internal` 以符合 .NET Framework 中字段的可访问性。

#### <a name="version-introduced"></a>引入的版本

3.0 RC1

#### <a name="recommended-action"></a>建议操作

如果开发的 .NET Core 应用的类型派生自 <xref:System.Windows.Forms.AccessibleObject>，访问 `RuntimeIDFirstItem` 字段时，此更改可能会对你产生影响。 如果是这种情况，可以按如下方式定义局部常量：

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>类别

Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

- 无法通过 API 分析检测到。

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->
