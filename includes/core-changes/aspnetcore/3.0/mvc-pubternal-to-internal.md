---
ms.openlocfilehash: 09fd95ba5f3aee59f2abdfbb4e64eb6202e2b873
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393944"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a><span data-ttu-id="a8098-101">MVC：“Pubternal”类型更改为内部</span><span class="sxs-lookup"><span data-stu-id="a8098-101">MVC: "Pubternal" types changed to internal</span></span>

<span data-ttu-id="a8098-102">在 ASP.NET Core 3.0 中，MVC 中的所有“pubternal”类型都已更新为 `public`（在受支持的命名空间中）或 `internal`（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="a8098-102">In ASP.NET Core 3.0, all "pubternal" types in MVC were updated to either be `public` in a supported namespace or `internal` as appropriate.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a8098-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="a8098-103">Change description</span></span>

<span data-ttu-id="a8098-104">在 ASP.NET Core 中，“pubternal”类型声明为 `public`，但驻留在后缀为 `.Internal` 的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="a8098-104">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a `.Internal`-suffixed namespace.</span></span> <span data-ttu-id="a8098-105">尽管这些类型为 `public`，但它们没有支持策略，并且可能会发生中断性变更。</span><span class="sxs-lookup"><span data-stu-id="a8098-105">While these types are `public`, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="a8098-106">遗憾的是，经常会意外使用这些类型，导致对这些项目做出中断性变更，并使维护框架的能力受到限制。</span><span class="sxs-lookup"><span data-stu-id="a8098-106">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a8098-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a8098-107">Version introduced</span></span>

<span data-ttu-id="a8098-108">3.0</span><span class="sxs-lookup"><span data-stu-id="a8098-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a8098-109">旧行为</span><span class="sxs-lookup"><span data-stu-id="a8098-109">Old behavior</span></span>

<span data-ttu-id="a8098-110">MVC 中的某些类型为 `public`，但在 `.Internal` 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="a8098-110">Some types in MVC were `public` but in a `.Internal` namespace.</span></span> <span data-ttu-id="a8098-111">这些类型没有支持策略，并且可能会发生中断性变更。</span><span class="sxs-lookup"><span data-stu-id="a8098-111">These types had no support policy and were subject to breaking changes.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a8098-112">新行为</span><span class="sxs-lookup"><span data-stu-id="a8098-112">New behavior</span></span>

<span data-ttu-id="a8098-113">所有此类类型都将更新为 `public`（在受支持的命名空间中）或标记为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="a8098-113">All such types are updated either to be `public` in a supported namespace or marked as `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a8098-114">更改原因</span><span class="sxs-lookup"><span data-stu-id="a8098-114">Reason for change</span></span>

<span data-ttu-id="a8098-115">经常会意外使用“pubternal”类型，导致对这些项目做出中断性变更，并使维护框架的能力受到限制。</span><span class="sxs-lookup"><span data-stu-id="a8098-115">Accidental use of the "pubternal" types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a8098-116">建议的操作</span><span class="sxs-lookup"><span data-stu-id="a8098-116">Recommended action</span></span>

<span data-ttu-id="a8098-117">如果使用的类型已真正成为 `public` 且已移动到新的受支持的命名空间中，请更新引用以匹配新命名空间。</span><span class="sxs-lookup"><span data-stu-id="a8098-117">If you're using types that have become truly `public` and have been moved into a new, supported namespace, update your references to match the new namespaces.</span></span>

<span data-ttu-id="a8098-118">如果使用的类型已标记为 `internal`，则需要查找替代方法。</span><span class="sxs-lookup"><span data-stu-id="a8098-118">If you're using types that have become marked as `internal`, you'll need to find an alternative.</span></span> <span data-ttu-id="a8098-119">永远不支持将以前的“pubternal”类型用于公共用途。</span><span class="sxs-lookup"><span data-stu-id="a8098-119">The previously "pubternal" types were never supported for public use.</span></span> <span data-ttu-id="a8098-120">如果这些命名空间中的特定类型对应用至关重要，请在 [aspnet/AspNetCore ](https://github.com/aspnet/AspNetCore/issues) 中提出问题。</span><span class="sxs-lookup"><span data-stu-id="a8098-120">If there are specific types in these namespaces that are critical to your apps, file an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span> <span data-ttu-id="a8098-121">可以考虑将请求的类型设为 `public`。</span><span class="sxs-lookup"><span data-stu-id="a8098-121">Considerations may be made for making the requested types `public`.</span></span>

#### <a name="category"></a><span data-ttu-id="a8098-122">类别</span><span class="sxs-lookup"><span data-stu-id="a8098-122">Category</span></span>

<span data-ttu-id="a8098-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a8098-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a8098-124">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a8098-124">Affected APIs</span></span>

<span data-ttu-id="a8098-125">此更改包括以下命名空间中的类型：</span><span class="sxs-lookup"><span data-stu-id="a8098-125">This change includes types in the following namespaces:</span></span>

- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

-->
