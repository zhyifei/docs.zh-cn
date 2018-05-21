---
title: 关于 .NET 微服务和 Web 应用中的授权
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 关于 .NET 微服务和 Web 应用中的授权
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 2ea56f5a28d115fc5d91a98604b82565c8bf5c78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="958d7-103">关于 .NET 微服务和 Web 应用中的授权</span><span class="sxs-lookup"><span data-stu-id="958d7-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="958d7-104">身份验证之后，ASP.NET Core Web API 需要授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="958d7-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="958d7-105">该过程允许服务向部分通过身份验证的用户提供 API，但不是向所有用户提供。</span><span class="sxs-lookup"><span data-stu-id="958d7-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="958d7-106">[身份验证](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)可基于用户角色或自定义策略完成，这可能包括检查声明或试探法。</span><span class="sxs-lookup"><span data-stu-id="958d7-106">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="958d7-107">限制 ASP.NET Core MVC 路由的访问权限十分简单，即将 Authorize 特性应用到操作方法（或者，如果所有控制器的操作都需要身份验证，则应用到控制器的类），如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="958d7-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="958d7-108">默认情况下，添加不具有参数的 Authorize 特性将限制已通过验证的用户对该控制器或操作的访问权限。</span><span class="sxs-lookup"><span data-stu-id="958d7-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="958d7-109">为了将 API 进一步限制于仅向特定用户提供，该特性可扩展为指定用户必须满足的必需角色或策略。</span><span class="sxs-lookup"><span data-stu-id="958d7-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="958d7-110">实现基于角色的身份验证</span><span class="sxs-lookup"><span data-stu-id="958d7-110">Implementing role-based authorization</span></span>

<span data-ttu-id="958d7-111">ASP.NET Core 标识具有角色的内置概念。</span><span class="sxs-lookup"><span data-stu-id="958d7-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="958d7-112">除了用户，ASP.NET Core 标识存储应用程序使用的不同角色的相关信息，并跟踪哪些用户分配到了哪些角色。</span><span class="sxs-lookup"><span data-stu-id="958d7-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="958d7-113">可以使用 RoleManager 类型（用于更新持久化储存中的角色）和 UserManager 类型（用于从角色分配或取消分配用户）以编程方式更改这些分配。</span><span class="sxs-lookup"><span data-stu-id="958d7-113">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="958d7-114">如果使用 JWT 持有者令牌进行身份验证，ASP.NET Core JWT 持有者身份验证中间件将基于令牌中找到的角色声明填充用户角色。</span><span class="sxs-lookup"><span data-stu-id="958d7-114">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="958d7-115">为了将对 MVC 操作或控制器的访问权限限制于特定角色中用户，可在 Authorize 标头中包含 Roles 参数，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="958d7-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

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

<span data-ttu-id="958d7-116">在此示例中，仅管理员或 PowerUser 角色中的用户可访问 ControlPanel 控制器中的 API（如执行设置时间操作）。</span><span class="sxs-lookup"><span data-stu-id="958d7-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="958d7-117">ShutDown API 进一步限制为仅允许访问 Adminstrator 角色的用户。</span><span class="sxs-lookup"><span data-stu-id="958d7-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="958d7-118">若要用户处于多种角色，则使用多个 Authorize 特性，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="958d7-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="958d7-119">在此示例中，要调用 API1，用户必须：</span><span class="sxs-lookup"><span data-stu-id="958d7-119">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="958d7-120">处于 Adminstrator 或 PowerUser 角色；</span><span class="sxs-lookup"><span data-stu-id="958d7-120">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="958d7-121">处于 RemoteEmployee 角色；</span><span class="sxs-lookup"><span data-stu-id="958d7-121">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="958d7-122">满足 CustomPolicy 授权的自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="958d7-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="958d7-123">实现基于策略的授权</span><span class="sxs-lookup"><span data-stu-id="958d7-123">Implementing policy-based authorization</span></span>

<span data-ttu-id="958d7-124">还可使用[授权策略](https://docs.asp.net/en/latest/security/authorization/policies.html)编写自定义授权规则。</span><span class="sxs-lookup"><span data-stu-id="958d7-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="958d7-125">我们在本节中进行了概述。</span><span class="sxs-lookup"><span data-stu-id="958d7-125">In this section we provide an overview.</span></span> <span data-ttu-id="958d7-126">详细信息可在 [ASP.NET 授权研讨会](https://github.com/blowdart/AspNetAuthorizationWorkshop)在线查看。</span><span class="sxs-lookup"><span data-stu-id="958d7-126">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="958d7-127">Startup.ConfigureServices 方法中使用 service.AddAuthorization 方法注册了自定义授权策略。</span><span class="sxs-lookup"><span data-stu-id="958d7-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="958d7-128">此方法采用了配置 AuthorizationOptions 参数的委托。</span><span class="sxs-lookup"><span data-stu-id="958d7-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="958d7-129">如示例所示，策略可与不同类型的要求相关联。</span><span class="sxs-lookup"><span data-stu-id="958d7-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="958d7-130">注册策略后，可通过将策略名称作为 Authorize 特性的 Policy 参数传递，将这些策略应用于操作或控制器（例如，\[Authorize(Policy="EmployeesOnly")\]），策略可有多个要求，而非仅有一个（如这些示例所示）。</span><span class="sxs-lookup"><span data-stu-id="958d7-130">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="958d7-131">在之前的示例中，第一个 AddPolicy 调用只是按角色授权的替代方式。</span><span class="sxs-lookup"><span data-stu-id="958d7-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="958d7-132">如果 \[Authorize(Policy="AdministratorsOnly")\] 应用于某个 API，则仅 Administrator 角色的用户能访问它。</span><span class="sxs-lookup"><span data-stu-id="958d7-132">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="958d7-133">第二个 AddPolicy 调用演示要求应该为用户提供特定声明所使用的一种简单方法。</span><span class="sxs-lookup"><span data-stu-id="958d7-133">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="958d7-134">RequireClaim 方法还可选择地采用声明的期望值。</span><span class="sxs-lookup"><span data-stu-id="958d7-134">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="958d7-135">如果指定了值，则仅当用户同时拥有正确类型的声明和某个指定值时才满足要求。</span><span class="sxs-lookup"><span data-stu-id="958d7-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="958d7-136">如果使用 JWT 持有者令牌身份验证中间件，则所有 JWT 属性都可用作用户声明。</span><span class="sxs-lookup"><span data-stu-id="958d7-136">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="958d7-137">本文所示的最有趣的策略是在第三个 AddPolicy 方法中，因为它使用了自定义授权要求。</span><span class="sxs-lookup"><span data-stu-id="958d7-137">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="958d7-138">通过使用自定义授权要求，可极大地控制授权的执行方式。</span><span class="sxs-lookup"><span data-stu-id="958d7-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="958d7-139">为此，必须实现这些类型：</span><span class="sxs-lookup"><span data-stu-id="958d7-139">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="958d7-140">从 IAuthorizationRequirement 派生并包含指定要求的详细信息的字段的要求类型。</span><span class="sxs-lookup"><span data-stu-id="958d7-140">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="958d7-141">在此示例中，这是用于示例 MinimumAgeRequirement 类型的年龄字段。</span><span class="sxs-lookup"><span data-stu-id="958d7-141">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="958d7-142">实现 AuthorizationHandler&lt;T&gt; 的处理程序，其中 T 是处理程序可满足的 IAuthorizationRequirement 的类型。</span><span class="sxs-lookup"><span data-stu-id="958d7-142">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="958d7-143">处理程序必须实现 HandleRequirementAsync 方法，该方法检查包含用户相关信息的指定上下文是否满足要求。</span><span class="sxs-lookup"><span data-stu-id="958d7-143">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="958d7-144">如果用户满足要求，对 context.Succeed 的调用将指示该用户已授权。</span><span class="sxs-lookup"><span data-stu-id="958d7-144">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="958d7-145">如果用户可能有多种方式满足授权要求，则可创建多个处理程序。</span><span class="sxs-lookup"><span data-stu-id="958d7-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="958d7-146">除使用 AddPolicy 调用注册自定义策略要求外，还需要通过依赖项注入注册自定义要求处理程序 (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;())。</span><span class="sxs-lookup"><span data-stu-id="958d7-146">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="958d7-147">ASP.NET Core [授权文档](https://docs.asp.net/en/latest/security/authorization/policies.html) 提供了用于（基于 DateOfBirth 声明）检查用户年龄的自定义授权要求和处理程序的示例。</span><span class="sxs-lookup"><span data-stu-id="958d7-147">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="958d7-148">其他资源</span><span class="sxs-lookup"><span data-stu-id="958d7-148">Additional resources</span></span>

-   <span data-ttu-id="958d7-149">**ASP.NET Core 身份验证**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="958d7-149">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="958d7-150">**ASP.NET Core 授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="958d7-150">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="958d7-151">**基于角色的授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="958d7-151">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="958d7-152">**基于自定义策略的授权**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="958d7-152">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="958d7-153">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="958d7-153">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
