---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394359"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>标识：UI 使用静态 Web 资产功能

ASP.NET Core 3.0 引入了静态 Web 资产功能，标识 UI 已采用此功能。

#### <a name="change-description"></a>更改描述

由于标识 UI 采用静态 Web 资产功能，因此：

- 可通过使用项目文件中的 `IdentityUIFrameworkVersion` 属性来完成框架选择。
- Bootstrap 4 是标识 UI 的默认 UI 框架。 Bootstrap 3 的生命周期已经结束，应考虑迁移到受支持的版本。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="old-behavior"></a>旧行为

标识 UI 的默认 UI 框架为 Bootstrap 3  。 可使用 `Startup.ConfigureServices` 中 `AddIdentityUI` 方法调用的参数配置 UI 框架。

#### <a name="new-behavior"></a>新行为

标识 UI 的默认 UI 框架为 Bootstrap 4  。 UI 框架必须在项目文件中进行配置，而不是在 `AddIdentityUI` 方法调用中配置。

#### <a name="reason-for-change"></a>更改原因

采用静态 Web 资产功能要求 UI 框架配置迁移到 MSBuild。 要在哪个框架上进行嵌入的决策是生成时决策，而非运行时决策。

#### <a name="recommended-action"></a>建议的操作

查看站点 UI，以确保新的 Bootstrap 4 组件兼容。 如有必要，请使用 `IdentityUIFrameworkVersion` MSBuild 属性还原为 Bootstrap 3。 将属性添加到项目文件中的 `<PropertyGroup>` 元素：

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>类别

ASP.NET Core

#### <a name="affected-apis"></a>受影响的 API

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->
