---
ms.openlocfilehash: 503d61cb86c83e2f32ad40c60a127ae255ef71b0
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198361"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="95106-101">MVC：从控制器操作名称中剪裁的异步后缀</span><span class="sxs-lookup"><span data-stu-id="95106-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="95106-102">作为寻址 [aspnet/AspNetCore#4849](https://github.com/aspnet/AspNetCore/issues/4849) 的一部分，ASP.NET Core MVC 默认从操作名称中剪裁后缀 `Async`。</span><span class="sxs-lookup"><span data-stu-id="95106-102">As part of addressing [aspnet/AspNetCore#4849](https://github.com/aspnet/AspNetCore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="95106-103">从 ASP.NET Core 3.0 开始，这一更改会影响路由和链接生成。</span><span class="sxs-lookup"><span data-stu-id="95106-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="95106-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="95106-104">Version introduced</span></span>

<span data-ttu-id="95106-105">3.0</span><span class="sxs-lookup"><span data-stu-id="95106-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="95106-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="95106-106">Old behavior</span></span>

<span data-ttu-id="95106-107">考虑以下 ASP.NET Core MVC 控制器：</span><span class="sxs-lookup"><span data-stu-id="95106-107">Consider the following ASP.NET Core MVC controller:</span></span>

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

<span data-ttu-id="95106-108">此操作可通过 `Product/ListAsync` 进行路由。</span><span class="sxs-lookup"><span data-stu-id="95106-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="95106-109">链接生成需要指定 `Async` 后缀。</span><span class="sxs-lookup"><span data-stu-id="95106-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="95106-110">例如:</span><span class="sxs-lookup"><span data-stu-id="95106-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="95106-111">新行为</span><span class="sxs-lookup"><span data-stu-id="95106-111">New behavior</span></span>

<span data-ttu-id="95106-112">在 ASP.NET Core 3.0 中，操作可通过 `Product/List` 进行路由。</span><span class="sxs-lookup"><span data-stu-id="95106-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="95106-113">链接生成代码应省略 `Async` 后缀。</span><span class="sxs-lookup"><span data-stu-id="95106-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="95106-114">例如:</span><span class="sxs-lookup"><span data-stu-id="95106-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="95106-115">此更改不会影响使用 `[ActionName]` 属性指定的名称。</span><span class="sxs-lookup"><span data-stu-id="95106-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="95106-116">可以通过在 `Startup.ConfigureServices` 中将 `MvcOptions.SuppressAsyncSuffixInActionNames` 设置为 `false` 来禁用新行为：</span><span class="sxs-lookup"><span data-stu-id="95106-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="95106-117">更改原因</span><span class="sxs-lookup"><span data-stu-id="95106-117">Reason for change</span></span>

<span data-ttu-id="95106-118">按照约定，异步 .NET 方法以 `Async` 为后缀。</span><span class="sxs-lookup"><span data-stu-id="95106-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="95106-119">但是，当方法定义 MVC 操作时，不需要使用 `Async` 后缀。</span><span class="sxs-lookup"><span data-stu-id="95106-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="95106-120">建议的操作</span><span class="sxs-lookup"><span data-stu-id="95106-120">Recommended action</span></span>

<span data-ttu-id="95106-121">如果应用依赖于保留名称的 `Async` 后缀的 MVC 操作，请选择下列缓解措施之一：</span><span class="sxs-lookup"><span data-stu-id="95106-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="95106-122">使用 `[ActionName]` 属性以保留原始名称。</span><span class="sxs-lookup"><span data-stu-id="95106-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="95106-123">通过在 `Startup.ConfigureServices` 中将 `MvcOptions.SuppressAsyncSuffixInActionNames` 设置为 `false` 来完全禁用重命名：</span><span class="sxs-lookup"><span data-stu-id="95106-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="95106-124">类别</span><span class="sxs-lookup"><span data-stu-id="95106-124">Category</span></span>

<span data-ttu-id="95106-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="95106-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95106-126">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="95106-126">Affected APIs</span></span>

<span data-ttu-id="95106-127">无</span><span class="sxs-lookup"><span data-stu-id="95106-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
