---
ms.openlocfilehash: 1e081c9f37fbd7ab754ce44ba89d7aa5cabfc219
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902063"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="505f5-101">MVC：预编译工具已弃用</span><span class="sxs-lookup"><span data-stu-id="505f5-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="505f5-102">在 ASP.NET Core 1.1 中，引入了 `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation`（MVC 预编译工具）包以添加对发布时进行 Razor 文件（.cshtml  文件）编译的支持。</span><span class="sxs-lookup"><span data-stu-id="505f5-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="505f5-103">在 ASP.NET Core 2.1 中，引入了 [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1)，以扩展预编译工具的功能。</span><span class="sxs-lookup"><span data-stu-id="505f5-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="505f5-104">Razor SDK 添加了对生成时和发布时进行 Razor 文件编译的支持。</span><span class="sxs-lookup"><span data-stu-id="505f5-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="505f5-105">SDK 在生成时验证 .cshtml  文件的正确性，同时缩短应用的启动时间。</span><span class="sxs-lookup"><span data-stu-id="505f5-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="505f5-106">默认情况下，Razor SDK 处于启用状态，并且不需要任何手势即可开始使用。</span><span class="sxs-lookup"><span data-stu-id="505f5-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="505f5-107">在 ASP.NET Core 3.0 中，已删除 ASP.NET Core 1.1 时代的 MVC 预编译工具。</span><span class="sxs-lookup"><span data-stu-id="505f5-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="505f5-108">早期的包版本将继续收到修补版本中的重要 Bug 和安全修补程序。</span><span class="sxs-lookup"><span data-stu-id="505f5-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="505f5-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="505f5-109">Version introduced</span></span>

<span data-ttu-id="505f5-110">3.0</span><span class="sxs-lookup"><span data-stu-id="505f5-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="505f5-111">旧行为</span><span class="sxs-lookup"><span data-stu-id="505f5-111">Old behavior</span></span>

<span data-ttu-id="505f5-112">`Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` 包用于预编译 MVC Razor 视图。</span><span class="sxs-lookup"><span data-stu-id="505f5-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="505f5-113">新行为</span><span class="sxs-lookup"><span data-stu-id="505f5-113">New behavior</span></span>

<span data-ttu-id="505f5-114">Razor SDK 本机支持此功能。</span><span class="sxs-lookup"><span data-stu-id="505f5-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="505f5-115">`Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` 包不再更新。</span><span class="sxs-lookup"><span data-stu-id="505f5-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="505f5-116">更改原因</span><span class="sxs-lookup"><span data-stu-id="505f5-116">Reason for change</span></span>

<span data-ttu-id="505f5-117">Razor SDK 提供更多的功能并在生成时验证 .cshtml  文件的正确性。</span><span class="sxs-lookup"><span data-stu-id="505f5-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="505f5-118">SDK 还会缩短应用的启动时间。</span><span class="sxs-lookup"><span data-stu-id="505f5-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="505f5-119">建议操作</span><span class="sxs-lookup"><span data-stu-id="505f5-119">Recommended action</span></span>

<span data-ttu-id="505f5-120">对于 ASP.NET Core 2.1 或更高版本的用户，更新以在 [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0) 中使用本机支持进行预编译。</span><span class="sxs-lookup"><span data-stu-id="505f5-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="505f5-121">如果 Bug 或缺失的功能阻止迁移到 Razor SDK，请在 [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) 中提出问题。</span><span class="sxs-lookup"><span data-stu-id="505f5-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="505f5-122">类别</span><span class="sxs-lookup"><span data-stu-id="505f5-122">Category</span></span>

<span data-ttu-id="505f5-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="505f5-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="505f5-124">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="505f5-124">Affected APIs</span></span>

<span data-ttu-id="505f5-125">None</span><span class="sxs-lookup"><span data-stu-id="505f5-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
