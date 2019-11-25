---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74100700"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Authorization:AddAuthorization 重载已移动到不同的程序集

用于驻留在 `Microsoft.AspNetCore.Authorization` 中的核心 `AddAuthorization` 方法已重命名为 `AddAuthorizationCore`。 旧的 `AddAuthorization` 方法仍然存在，但却在 `Microsoft.AspNetCore.Authorization.Policy` 程序集中。 使用这两种方法的应用应该不会受到任何影响。 请注意，`Microsoft.AspNetCore.Authorization.Policy` 现随附于共享框架而不是独立的包中，如[共享框架：从 Microsoft.AspNetCore.App 中删除了程序集](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)中所述。

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
