---
title: "有关在.NET 微服务和 web 应用程序的授权"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |有关在.NET 微服务和 web 应用程序的授权"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 51adda4f5bdb28154f17b9a988ee2d887bf1d461
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>有关在.NET 微服务和 web 应用程序的授权

身份验证后，ASP.NET 核心 Web Api 需要授予访问权限。 此进程允许服务以使 Api 可供某些经过身份验证的用户，而不是为全部。 [授权](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)可以根据用户的角色或基于自定义策略，这可能包括检查声明或其他试探方法。

将访问限制为 ASP.NET 核心 MVC 路由是简单地将 Authorize 属性中所示下面的示例作为到操作方法 （或如果所有控制器操作需要授权的控制器的类），应用：

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

默认情况下，通过添加 Authorize 特性不带参数将限制该控制器或操作对身份验证的用户的访问。 若要进一步限制为可供只有特定用户的 API，可展开该属性以指定所需的角色或用户必须满足的策略。

## <a name="implementing-role-based-authorization"></a>实现基于角色的授权

ASP.NET 核心标识具有了内置的角色概念。 除了用户，ASP.NET 核心标识存储有关应用程序所使用的不同角色的信息和跟踪哪些用户分配给哪些角色。 使用 RoleManager 类型 （这会更新持久性存储区中的角色） 和 UserManager 类型 （它可以分配或取消分配用户角色），可以以编程方式更改这些分配。

如果使用 JWT 持有者令牌进行身份验证你，ASP.NET 核心 JWT 持有者身份验证中间件将填充基于令牌中找到的角色声明的用户的角色。 若要限制的 MVC 操作或在特定角色中向用户的控制器的访问，可以包括角色参数中的授权标头，，如下面的示例中所示：

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

在此示例中，只有管理员或 PowerUser 角色中的用户可以访问控制面板控制器 （如执行 SetTime 操作） 中的 Api。 关闭 API 进一步限制为只允许访问用户的管理员角色中。

若要要求用户是在多个角色，你使用多个 Authorize 属性，如下面的示例中所示：

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

在此示例中，若要调用 API1，用户必须：

-   处于管理员*或*PowerUser 角色*和*

-   处于 RemoteEmployee 角色，*和*

-   满足的自定义处理程序 CustomPolicy 授权。

## <a name="implementing-policy-based-authorization"></a>实现基于策略的授权

此外可以使用编写自定义授权规则[授权策略](https://docs.asp.net/en/latest/security/authorization/policies.html)。 在本部分中，我们提供了概述。 更多详细信息可用于在线[ASP.NET 授权研讨会](https://github.com/blowdart/AspNetAuthorizationWorkshop)。

自定义授权策略在 Startup.ConfigureServices 方法中使用服务注册。AddAuthorization 方法。 此方法采用委托，用于配置 AuthorizationOptions 自变量。

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));
    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));
    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

该示例中所示，策略可能与不同类型的要求。 注册策略后，它们可以应用于操作或控制器通过将策略的名称传递作为 Authorize 属性的策略自变量 (例如， \[Authorize(Policy="EmployeesOnly")\]) 可以有策略多个要求，而不仅仅是一个 （如这些示例中所示）。

在前面的示例中，第一次 AddPolicy 调用是只需按角色授权一种替代方式。 如果\[Authorize(Policy="AdministratorsOnly")\]将应用于一个 API 中，只有管理员角色中的用户将能够访问它。

第二个 AddPolicy 调用演示需要特定的声明，应会显示用户的简单办法。 RequireClaim 方法也采用声明的预期值。 如果指定值，仅当用户具有两个一个声明的正确类型和指定的值之一来满足该要求。 如果你使用 JWT 持有者身份验证中间件，所有 JWT 属性都将用作用户声明。

此处显示的最有趣策略是在第三个 AddPolicy 方法中，因为它使用自定义的授权要求。 通过使用自定义的授权要求，你可以大量控制如何执行授权。 对于这种方式生效，必须实现这些类型：

-   要求类型的派生自 IAuthorizationRequirement 和，其中包含指定要求的详细信息的字段。 在示例中，这是示例 MinimumAgeRequirement 类型的年龄字段。

-   处理程序实现 AuthorizationHandler&lt;T&gt;，其中 T 为 IAuthorizationRequirement 处理程序可以满足的类型。 处理程序必须实现 HandleRequirementAsync 方法，此检查指定的上下文，其中包含有关用户的信息是否满足要求。

如果该用户满足的要求，对上下文的调用。成功将指示是否授权该用户。 如果有多个用户可能满足授权要求的方式，可以创建多个处理程序。

除了注册 AddPolicy 调用自定义策略要求，你还需要注册自定义要求处理程序通过依赖关系注入 （服务。AddTransient&lt;IAuthorizationHandler、 MinimumAgeHandler&gt;（)）。

自定义的授权要求和处理程序检查用户的年龄 （基于 DateOfBirth 声明） 的示例可用于 ASP.NET Core[授权文档](https://docs.asp.net/en/latest/security/authorization/policies.html)。

## <a name="additional-resources"></a>其他资源

-   **ASP.NET 核心身份验证**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **ASP.NET 核心授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)

-   **基于角色的授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)

-   **自定义的基于策略的授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)




>[!div class="step-by-step"]
[以前](index.md) [下一步] (开发人员的应用程序的机密-storage.md)
