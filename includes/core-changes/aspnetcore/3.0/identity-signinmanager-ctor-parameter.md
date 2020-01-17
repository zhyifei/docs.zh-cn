---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901822"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>标识：SignInManager 构造函数接受新参数

从 ASP.NET Core 3.0 开始，新的 `IUserConfirmation<TUser>` 参数添加到了 `SignInManager` 构造函数中。 有关详细信息，请参阅 [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356)。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="reason-for-change"></a>更改原因

更改的动机是为了添加对标识中的新电子邮件/确认流的支持。

#### <a name="recommended-action"></a>建议操作

如果手动构造 `SignInManager`，请提供 `IUserConfirmation` 的实现，或从依赖项注入获取一个实现来提供。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
