---
ms.openlocfilehash: 8cb0aca991f5adfe4561ef56090cb9f7b2e56283
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901612"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a><span data-ttu-id="3a183-101">本地化：ResourceManagerWithCultureStringLocalizer 和 WithCulture 被标记为过时</span><span class="sxs-lookup"><span data-stu-id="3a183-101">Localization: ResourceManagerWithCultureStringLocalizer and WithCulture marked obsolete</span></span>

<span data-ttu-id="3a183-102">[ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) 类和 [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) 接口成员通常是造成本地化用户混淆的原因，尤其是在创建自己的 `IStringLocalizer` 实现时。</span><span class="sxs-lookup"><span data-stu-id="3a183-102">The [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) class and [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) interface member are often sources of confusion for users of localization, especially when creating their own `IStringLocalizer` implementation.</span></span> <span data-ttu-id="3a183-103">这些项给用户留下了 `IStringLocalizer` 实例“按语言、按资源”的印象。</span><span class="sxs-lookup"><span data-stu-id="3a183-103">These items give the user the impression that an `IStringLocalizer` instance is "per-language, per-resource".</span></span> <span data-ttu-id="3a183-104">实际上，实例应该仅“按资源”。</span><span class="sxs-lookup"><span data-stu-id="3a183-104">In reality, the instances should only be "per-resource".</span></span> <span data-ttu-id="3a183-105">搜索的语言由 `CultureInfo.CurrentUICulture` 在执行时确定。</span><span class="sxs-lookup"><span data-stu-id="3a183-105">The language searched for is determined by the `CultureInfo.CurrentUICulture` at execution time.</span></span> <span data-ttu-id="3a183-106">为了消除混淆来源，这些 API 在 ASP.NET Core 3.0 Preview 3 中被标记为过时。</span><span class="sxs-lookup"><span data-stu-id="3a183-106">To eliminate the source of confusion, the APIs were marked as obsolete in ASP.NET Core 3.0 Preview 3.</span></span> <span data-ttu-id="3a183-107">将从未来版本中删除这些 API。</span><span class="sxs-lookup"><span data-stu-id="3a183-107">The APIs will be removed in a future release.</span></span>

<span data-ttu-id="3a183-108">有关上下文，请参阅 [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324)。</span><span class="sxs-lookup"><span data-stu-id="3a183-108">For context, see [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="3a183-109">有关讨论，请参阅 [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756)。</span><span class="sxs-lookup"><span data-stu-id="3a183-109">For discussion, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3a183-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="3a183-110">Version introduced</span></span>

<span data-ttu-id="3a183-111">3.0</span><span class="sxs-lookup"><span data-stu-id="3a183-111">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3a183-112">旧行为</span><span class="sxs-lookup"><span data-stu-id="3a183-112">Old behavior</span></span>

<span data-ttu-id="3a183-113">方法未标记为 `Obsolete`。</span><span class="sxs-lookup"><span data-stu-id="3a183-113">Methods weren't marked as `Obsolete`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3a183-114">新行为</span><span class="sxs-lookup"><span data-stu-id="3a183-114">New behavior</span></span>

<span data-ttu-id="3a183-115">方法被标记为 `Obsolete`。</span><span class="sxs-lookup"><span data-stu-id="3a183-115">Methods are marked `Obsolete`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3a183-116">更改原因</span><span class="sxs-lookup"><span data-stu-id="3a183-116">Reason for change</span></span>

<span data-ttu-id="3a183-117">API 表示一个不推荐使用的用例。</span><span class="sxs-lookup"><span data-stu-id="3a183-117">The APIs represented a use case that isn't recommended.</span></span> <span data-ttu-id="3a183-118">本地化设计存在混淆。</span><span class="sxs-lookup"><span data-stu-id="3a183-118">There was confusion about the design of localization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3a183-119">建议操作</span><span class="sxs-lookup"><span data-stu-id="3a183-119">Recommended action</span></span>

<span data-ttu-id="3a183-120">建议改用 `ResourceManagerStringLocalizer`。</span><span class="sxs-lookup"><span data-stu-id="3a183-120">The recommendation is to use `ResourceManagerStringLocalizer` instead.</span></span> <span data-ttu-id="3a183-121">允许 `CurrentCulture` 设置区域性。</span><span class="sxs-lookup"><span data-stu-id="3a183-121">Let the culture be set by the `CurrentCulture`.</span></span> <span data-ttu-id="3a183-122">如果没有这个选项，请创建并使用 [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) 的副本。</span><span class="sxs-lookup"><span data-stu-id="3a183-122">If that isn't an option, create and use a copy of [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).</span></span>

#### <a name="category"></a><span data-ttu-id="3a183-123">类别</span><span class="sxs-lookup"><span data-stu-id="3a183-123">Category</span></span>

<span data-ttu-id="3a183-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a183-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a183-125">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="3a183-125">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
