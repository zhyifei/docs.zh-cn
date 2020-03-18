---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901718"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="ad228-101">托管：ObjectPoolProvider 已从 WebHostBuilder 依赖项中删除</span><span class="sxs-lookup"><span data-stu-id="ad228-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="ad228-102">作为使 ASP.NET Core 更具成本效益计划的一部分，`ObjectPoolProvider` 已从主要依赖项集中删除。</span><span class="sxs-lookup"><span data-stu-id="ad228-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="ad228-103">依赖于 `ObjectPoolProvider` 的特定组件现在会自行添加。</span><span class="sxs-lookup"><span data-stu-id="ad228-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="ad228-104">有关讨论，请参阅 [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944)。</span><span class="sxs-lookup"><span data-stu-id="ad228-104">For discussion, see [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ad228-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ad228-105">Version introduced</span></span>

<span data-ttu-id="ad228-106">3.0</span><span class="sxs-lookup"><span data-stu-id="ad228-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ad228-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="ad228-107">Old behavior</span></span>

<span data-ttu-id="ad228-108">`WebHostBuilder` 默认在 DI 容器中提供 `ObjectPoolProvider`。</span><span class="sxs-lookup"><span data-stu-id="ad228-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ad228-109">新行为</span><span class="sxs-lookup"><span data-stu-id="ad228-109">New behavior</span></span>

<span data-ttu-id="ad228-110">`WebHostBuilder` 默认不再在 DI 容器中提供 `ObjectPoolProvider`。</span><span class="sxs-lookup"><span data-stu-id="ad228-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ad228-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="ad228-111">Reason for change</span></span>

<span data-ttu-id="ad228-112">进行此更改是为了使 ASP.NET Core 更具成本效益。</span><span class="sxs-lookup"><span data-stu-id="ad228-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ad228-113">建议操作</span><span class="sxs-lookup"><span data-stu-id="ad228-113">Recommended action</span></span>

<span data-ttu-id="ad228-114">如果组件需要 `ObjectPoolProvider`，则需要通过 `IServiceCollection` 将其添加到依赖项。</span><span class="sxs-lookup"><span data-stu-id="ad228-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="ad228-115">类别</span><span class="sxs-lookup"><span data-stu-id="ad228-115">Category</span></span>

<span data-ttu-id="ad228-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ad228-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad228-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="ad228-117">Affected APIs</span></span>

<span data-ttu-id="ad228-118">None</span><span class="sxs-lookup"><span data-stu-id="ad228-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
