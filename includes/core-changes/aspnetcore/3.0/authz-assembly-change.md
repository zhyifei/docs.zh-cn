---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394136"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Authorization:AddAuthorization 重载已移动到不同的程序集

用于驻留在 `Microsoft.AspNetCore.Authorization` 中的核心 `AddAuthorization` 方法已重命名为 `AddAuthorizationCore`。 旧的 `AddAuthorization` 方法仍然存在，但却在 `Microsoft.AspNetCore.Authorization.Policy` 包中。 使用这两种方法的应用应该不会受到任何影响。 未使用策略包的应用必须切换为使用 `AddAuthorizationCore`。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

`Microsoft.AspNetCore.Authorization` 中已存在 `AddAuthorization` 方法。

#### <a name="new-behavior"></a>新行为

`Microsoft.AspNetCore.Authorization.Policy` 中存在 `AddAuthorization` 方法。 `AddAuthorizationCore` 是旧方法的新名称。

#### <a name="reason-for-change"></a>更改原因

`AddAuthorization` 是一个更好的方法名称，用于添加授权所需的所有常用服务。

#### <a name="recommended-action"></a>建议的操作

添加对 `Microsoft.AspNetCore.Authorization.Policy` 的引用或改用 `AddAuthorizationCore`。

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
