---
ms.openlocfilehash: da1ec7908b3082fc61313cb805773aa600bc1b5d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393921"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>本地化：ResourceManagerWithCultureStringLocalizer 和 WithCulture 被标记为过时

[ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) 类和 [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) 接口成员通常是造成本地化用户混淆的原因，尤其是在创建自己的 `IStringLocalizer` 实现时。 这些项给用户留下了 `IStringLocalizer` 实例“按语言、按资源”的印象。 实际上，实例应该仅“按资源”。 搜索的语言由 `CultureInfo.CurrentUICulture` 在执行时确定。 为了消除混淆来源，这些 API 在 ASP.NET Core 3.0 Preview 3 中被标记为过时。 将从未来版本中删除这些 API。

有关上下文，请参阅 [aspnet/AspNetCore # 3324](https://github.com/aspnet/AspNetCore/issues/3324)。 有关讨论，请参阅 [aspnet/AspNetCore#7756](https://github.com/aspnet/AspNetCore/issues/7756)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

方法未标记为 `Obsolete`。

#### <a name="new-behavior"></a>新行为

方法被标记为 `Obsolete`。

#### <a name="reason-for-change"></a>更改原因

API 表示一个不推荐使用的用例。 本地化设计存在混淆。

#### <a name="recommended-action"></a>建议的操作

建议改用 `ResourceManagerStringLocalizer`。 允许 `CurrentCulture` 设置区域性。 如果没有这个选项，请创建并使用 [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) 的副本。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
