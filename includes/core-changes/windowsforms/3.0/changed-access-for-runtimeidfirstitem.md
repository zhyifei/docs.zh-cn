---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643927"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>更改访问 AccessibleObject.RuntimeIDFirstItem 的权限

从 .NET Core 3.0 RC1 开始，`AccessibleObject.RuntimeIDFirstItem` 的可访问性已从 `protected` 更改为 `internal`。

#### <a name="change-description"></a>更改描述

从 .NET Core 3.0 预览版 4 开始，`AccessibleObject.RuntimeIDFirstItem` 字段为 `protected`。 从 .NET Core 3.0 RC1 开始，它已从 `protected` 更改为 `internal` 以符合 .NET Framework 中字段的可访问性。

#### <a name="version-introduced"></a>引入的版本

3.0 RC1

#### <a name="recommended-action"></a>建议的操作

如果开发的 .NET Core 应用的类型派生自 <xref:System.Windows.Forms.AccessibleObject>，访问 `RuntimeIDFirstItem` 字段时，此更改可能会对你产生影响。 如果是这种情况，可以按如下方式定义局部常量：

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>类别

Windows 窗体

#### <a name="affected-apis"></a>受影响的 API

- 无法通过 API 分析检测到。

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
