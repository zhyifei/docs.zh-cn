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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="8654e-104">有关在.NET 微服务和 web 应用程序的授权</span><span class="sxs-lookup"><span data-stu-id="8654e-104">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="8654e-105">身份验证后，ASP.NET 核心 Web Api 需要授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="8654e-105">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="8654e-106">此进程允许服务以使 Api 可供某些经过身份验证的用户，而不是为全部。</span><span class="sxs-lookup"><span data-stu-id="8654e-106">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="8654e-107">[授权](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)可以根据用户的角色或基于自定义策略，这可能包括检查声明或其他试探方法。</span><span class="sxs-lookup"><span data-stu-id="8654e-107">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="8654e-108">将访问限制为 ASP.NET 核心 MVC 路由是简单地将 Authorize 属性中所示下面的示例作为到操作方法 （或如果所有控制器操作需要授权的控制器的类），应用：</span><span class="sxs-lookup"><span data-stu-id="8654e-108">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="8654e-109">默认情况下，通过添加 Authorize 特性不带参数将限制该控制器或操作对身份验证的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="8654e-109">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="8654e-110">若要进一步限制为可供只有特定用户的 API，可展开该属性以指定所需的角色或用户必须满足的策略。</span><span class="sxs-lookup"><span data-stu-id="8654e-110">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="8654e-111">实现基于角色的授权</span><span class="sxs-lookup"><span data-stu-id="8654e-111">Implementing role-based authorization</span></span>

<span data-ttu-id="8654e-112">ASP.NET 核心标识具有了内置的角色概念。</span><span class="sxs-lookup"><span data-stu-id="8654e-112">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="8654e-113">除了用户，ASP.NET 核心标识存储有关应用程序所使用的不同角色的信息和跟踪哪些用户分配给哪些角色。</span><span class="sxs-lookup"><span data-stu-id="8654e-113">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="8654e-114">使用 RoleManager 类型 （这会更新持久性存储区中的角色） 和 UserManager 类型 （它可以分配或取消分配用户角色），可以以编程方式更改这些分配。</span><span class="sxs-lookup"><span data-stu-id="8654e-114">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="8654e-115">如果使用 JWT 持有者令牌进行身份验证你，ASP.NET 核心 JWT 持有者身份验证中间件将填充基于令牌中找到的角色声明的用户的角色。</span><span class="sxs-lookup"><span data-stu-id="8654e-115">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="8654e-116">若要限制的 MVC 操作或在特定角色中向用户的控制器的访问，可以包括角色参数中的授权标头，，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8654e-116">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

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

<span data-ttu-id="8654e-117">在此示例中，只有管理员或 PowerUser 角色中的用户可以访问控制面板控制器 （如执行 SetTime 操作） 中的 Api。</span><span class="sxs-lookup"><span data-stu-id="8654e-117">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="8654e-118">关闭 API 进一步限制为只允许访问用户的管理员角色中。</span><span class="sxs-lookup"><span data-stu-id="8654e-118">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="8654e-119">若要要求用户是在多个角色，你使用多个 Authorize 属性，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8654e-119">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="8654e-120">在此示例中，若要调用 API1，用户必须：</span><span class="sxs-lookup"><span data-stu-id="8654e-120">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="8654e-121">处于管理员*或*PowerUser 角色*和*</span><span class="sxs-lookup"><span data-stu-id="8654e-121">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="8654e-122">处于 RemoteEmployee 角色，*和*</span><span class="sxs-lookup"><span data-stu-id="8654e-122">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="8654e-123">满足的自定义处理程序 CustomPolicy 授权。</span><span class="sxs-lookup"><span data-stu-id="8654e-123">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="8654e-124">实现基于策略的授权</span><span class="sxs-lookup"><span data-stu-id="8654e-124">Implementing policy-based authorization</span></span>

<span data-ttu-id="8654e-125">此外可以使用编写自定义授权规则[授权策略](https://docs.asp.net/en/latest/security/authorization/policies.html)。</span><span class="sxs-lookup"><span data-stu-id="8654e-125">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="8654e-126">在本部分中，我们提供了概述。</span><span class="sxs-lookup"><span data-stu-id="8654e-126">In this section we provide an overview.</span></span> <span data-ttu-id="8654e-127">更多详细信息可用于在线[ASP.NET 授权研讨会](https://github.com/blowdart/AspNetAuthorizationWorkshop)。</span><span class="sxs-lookup"><span data-stu-id="8654e-127">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="8654e-128">自定义授权策略在 Startup.ConfigureServices 方法中使用服务注册。AddAuthorization 方法。</span><span class="sxs-lookup"><span data-stu-id="8654e-128">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="8654e-129">此方法采用委托，用于配置 AuthorizationOptions 自变量。</span><span class="sxs-lookup"><span data-stu-id="8654e-129">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="8654e-130">该示例中所示，策略可能与不同类型的要求。</span><span class="sxs-lookup"><span data-stu-id="8654e-130">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="8654e-131">注册策略后，它们可以应用于操作或控制器通过将策略的名称传递作为 Authorize 属性的策略自变量 (例如， \[Authorize(Policy="EmployeesOnly")\]) 可以有策略多个要求，而不仅仅是一个 （如这些示例中所示）。</span><span class="sxs-lookup"><span data-stu-id="8654e-131">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="8654e-132">在前面的示例中，第一次 AddPolicy 调用是只需按角色授权一种替代方式。</span><span class="sxs-lookup"><span data-stu-id="8654e-132">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="8654e-133">如果\[Authorize(Policy="AdministratorsOnly")\]将应用于一个 API 中，只有管理员角色中的用户将能够访问它。</span><span class="sxs-lookup"><span data-stu-id="8654e-133">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="8654e-134">第二个 AddPolicy 调用演示需要特定的声明，应会显示用户的简单办法。</span><span class="sxs-lookup"><span data-stu-id="8654e-134">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="8654e-135">RequireClaim 方法也采用声明的预期值。</span><span class="sxs-lookup"><span data-stu-id="8654e-135">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="8654e-136">如果指定值，仅当用户具有两个一个声明的正确类型和指定的值之一来满足该要求。</span><span class="sxs-lookup"><span data-stu-id="8654e-136">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="8654e-137">如果你使用 JWT 持有者身份验证中间件，所有 JWT 属性都将用作用户声明。</span><span class="sxs-lookup"><span data-stu-id="8654e-137">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="8654e-138">此处显示的最有趣策略是在第三个 AddPolicy 方法中，因为它使用自定义的授权要求。</span><span class="sxs-lookup"><span data-stu-id="8654e-138">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="8654e-139">通过使用自定义的授权要求，你可以大量控制如何执行授权。</span><span class="sxs-lookup"><span data-stu-id="8654e-139">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="8654e-140">对于这种方式生效，必须实现这些类型：</span><span class="sxs-lookup"><span data-stu-id="8654e-140">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="8654e-141">要求类型的派生自 IAuthorizationRequirement 和，其中包含指定要求的详细信息的字段。</span><span class="sxs-lookup"><span data-stu-id="8654e-141">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="8654e-142">在示例中，这是示例 MinimumAgeRequirement 类型的年龄字段。</span><span class="sxs-lookup"><span data-stu-id="8654e-142">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="8654e-143">处理程序实现 AuthorizationHandler&lt;T&gt;，其中 T 为 IAuthorizationRequirement 处理程序可以满足的类型。</span><span class="sxs-lookup"><span data-stu-id="8654e-143">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="8654e-144">处理程序必须实现 HandleRequirementAsync 方法，此检查指定的上下文，其中包含有关用户的信息是否满足要求。</span><span class="sxs-lookup"><span data-stu-id="8654e-144">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="8654e-145">如果该用户满足的要求，对上下文的调用。成功将指示是否授权该用户。</span><span class="sxs-lookup"><span data-stu-id="8654e-145">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="8654e-146">如果有多个用户可能满足授权要求的方式，可以创建多个处理程序。</span><span class="sxs-lookup"><span data-stu-id="8654e-146">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="8654e-147">除了注册 AddPolicy 调用自定义策略要求，你还需要注册自定义要求处理程序通过依赖关系注入 （服务。AddTransient&lt;IAuthorizationHandler、 MinimumAgeHandler&gt;（)）。</span><span class="sxs-lookup"><span data-stu-id="8654e-147">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="8654e-148">自定义的授权要求和处理程序检查用户的年龄 （基于 DateOfBirth 声明） 的示例可用于 ASP.NET Core[授权文档](https://docs.asp.net/en/latest/security/authorization/policies.html)。</span><span class="sxs-lookup"><span data-stu-id="8654e-148">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8654e-149">其他资源</span><span class="sxs-lookup"><span data-stu-id="8654e-149">Additional resources</span></span>

-   <span data-ttu-id="8654e-150">**ASP.NET 核心身份验证**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="8654e-150">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="8654e-151">**ASP.NET 核心授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="8654e-151">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="8654e-152">**基于角色的授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="8654e-152">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="8654e-153">**自定义的基于策略的授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="8654e-153">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="8654e-154">[以前](index.md) [下一步] (开发人员的应用程序的机密-storage.md)</span><span class="sxs-lookup"><span data-stu-id="8654e-154">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
