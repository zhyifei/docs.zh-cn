---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901991"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a><span data-ttu-id="7df9a-101">授权：从 AuthorizationFilterContext.Filters 中删除 IAllowAnonymous</span><span class="sxs-lookup"><span data-stu-id="7df9a-101">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>

<span data-ttu-id="7df9a-102">从 ASP.NET Core 3.0 起，MVC 不会为在控制器和操作方法上发现的 [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) 属性添加 [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter)。</span><span class="sxs-lookup"><span data-stu-id="7df9a-102">As of ASP.NET Core 3.0, MVC doesn't add [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) for [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributes that were discovered on controllers and action methods.</span></span> <span data-ttu-id="7df9a-103">此更改针对 <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute> 派生在本地进行处理，但对于 <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> 和 <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> 实现来说是一个重大变更。</span><span class="sxs-lookup"><span data-stu-id="7df9a-103">This change is addressed locally for derivatives of <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, but it's a breaking change for <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> and <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementations.</span></span> <span data-ttu-id="7df9a-104">包装在 [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) 属性中的此类实现是在需要配置和依赖项注入时实现强类型的基于属性的授权的[常见](https://stackoverflow.com/a/41348219/608220)的支持方式。</span><span class="sxs-lookup"><span data-stu-id="7df9a-104">Such implementations wrapped in a [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) attribute are a [popular](https://stackoverflow.com/a/41348219/608220) and supported way to achieve strongly-typed, attribute-based authorization when both configuration and dependency injection are required.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7df9a-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="7df9a-105">Version introduced</span></span>

<span data-ttu-id="7df9a-106">3.0</span><span class="sxs-lookup"><span data-stu-id="7df9a-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7df9a-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="7df9a-107">Old behavior</span></span>

<span data-ttu-id="7df9a-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> 出现在 [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) 集合中。</span><span class="sxs-lookup"><span data-stu-id="7df9a-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> appeared in the [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) collection.</span></span> <span data-ttu-id="7df9a-109">对接口的状态进行测试是对单个控制器方法上的筛选器进行重写或禁用的一种有效方法。</span><span class="sxs-lookup"><span data-stu-id="7df9a-109">Testing for the interface's presence was a valid approach to override or disable the filter on individual controller methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7df9a-110">新行为</span><span class="sxs-lookup"><span data-stu-id="7df9a-110">New behavior</span></span>

<span data-ttu-id="7df9a-111">`IAllowAnonymous` 不再出现在 `AuthorizationFilterContext.Filters` 集合中。</span><span class="sxs-lookup"><span data-stu-id="7df9a-111">`IAllowAnonymous` no longer appears in the `AuthorizationFilterContext.Filters` collection.</span></span> <span data-ttu-id="7df9a-112">依赖于旧行为的 `IAsyncAuthorizationFilter` 实现通常导致间歇性 HTTP 401 未授权或 HTTP 403 禁止响应。</span><span class="sxs-lookup"><span data-stu-id="7df9a-112">`IAsyncAuthorizationFilter` implementations that are dependent on the old behavior typically cause intermittent HTTP 401 Unauthorized or HTTP 403 Forbidden responses.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7df9a-113">更改原因</span><span class="sxs-lookup"><span data-stu-id="7df9a-113">Reason for change</span></span>

<span data-ttu-id="7df9a-114">ASP.NET Core 3.0 中引入了新的终结点路由策略。</span><span class="sxs-lookup"><span data-stu-id="7df9a-114">A new endpoint routing strategy was introduced in ASP.NET Core 3.0.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7df9a-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="7df9a-115">Recommended action</span></span>

<span data-ttu-id="7df9a-116">在终结点元数据中搜索 `IAllowAnonymous`。</span><span class="sxs-lookup"><span data-stu-id="7df9a-116">Search the endpoint metadata for `IAllowAnonymous`.</span></span> <span data-ttu-id="7df9a-117">例如：</span><span class="sxs-lookup"><span data-stu-id="7df9a-117">For example:</span></span>

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

<span data-ttu-id="7df9a-118">[此 HasAllowAnonymous 方法](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236)中演示了此方法。</span><span class="sxs-lookup"><span data-stu-id="7df9a-118">An example of this technique is seen in [this HasAllowAnonymous method](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span></span>

#### <a name="category"></a><span data-ttu-id="7df9a-119">类别</span><span class="sxs-lookup"><span data-stu-id="7df9a-119">Category</span></span>

<span data-ttu-id="7df9a-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7df9a-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7df9a-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="7df9a-121">Affected APIs</span></span>

<span data-ttu-id="7df9a-122">None</span><span class="sxs-lookup"><span data-stu-id="7df9a-122">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
