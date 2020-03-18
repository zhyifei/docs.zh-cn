---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394480"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a><span data-ttu-id="9e7bd-101">SPA：SpaServices 和 NodeServices 被标记为过时</span><span class="sxs-lookup"><span data-stu-id="9e7bd-101">SPAs: SpaServices and NodeServices marked obsolete</span></span>

<span data-ttu-id="9e7bd-102">自 ASP.NET Core 2.1 起，以下 NuGet 包的内容都是不必要的。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-102">The contents of the following NuGet packages have all been unnecessary since ASP.NET Core 2.1.</span></span> <span data-ttu-id="9e7bd-103">因此，下列包将被标记为过时：</span><span class="sxs-lookup"><span data-stu-id="9e7bd-103">Consequently, the following packages are being marked as obsolete:</span></span>

- [<span data-ttu-id="9e7bd-104">Microsoft.AspNetCore.SpaServices</span><span class="sxs-lookup"><span data-stu-id="9e7bd-104">Microsoft.AspNetCore.SpaServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [<span data-ttu-id="9e7bd-105">Microsoft.AspNetCore.NodeServices</span><span class="sxs-lookup"><span data-stu-id="9e7bd-105">Microsoft.AspNetCore.NodeServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

<span data-ttu-id="9e7bd-106">出于相同的原因，以下 npm 模块将被标记为已弃用：</span><span class="sxs-lookup"><span data-stu-id="9e7bd-106">For the same reason, the following npm modules are being marked as deprecated:</span></span>

- [<span data-ttu-id="9e7bd-107">aspnet-angular</span><span class="sxs-lookup"><span data-stu-id="9e7bd-107">aspnet-angular</span></span>](https://www.npmjs.com/package/aspnet-angular)
- [<span data-ttu-id="9e7bd-108">aspnet-prerendering</span><span class="sxs-lookup"><span data-stu-id="9e7bd-108">aspnet-prerendering</span></span>](https://www.npmjs.com/package/aspnet-prerendering)
- [<span data-ttu-id="9e7bd-109">aspnet-webpack</span><span class="sxs-lookup"><span data-stu-id="9e7bd-109">aspnet-webpack</span></span>](https://www.npmjs.com/package/aspnet-webpack)
- [<span data-ttu-id="9e7bd-110">aspnet-webpack-react</span><span class="sxs-lookup"><span data-stu-id="9e7bd-110">aspnet-webpack-react</span></span>](https://www.npmjs.com/package/aspnet-webpack-react)
- [<span data-ttu-id="9e7bd-111">domain-task</span><span class="sxs-lookup"><span data-stu-id="9e7bd-111">domain-task</span></span>](https://www.npmjs.com/package/domain-task)

<span data-ttu-id="9e7bd-112">上述包和 npm 模块稍后将从 .NET 5 中删除。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-112">The preceding packages and npm modules will later be removed in .NET 5.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9e7bd-113">引入的版本</span><span class="sxs-lookup"><span data-stu-id="9e7bd-113">Version introduced</span></span>

<span data-ttu-id="9e7bd-114">3.0</span><span class="sxs-lookup"><span data-stu-id="9e7bd-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9e7bd-115">旧行为</span><span class="sxs-lookup"><span data-stu-id="9e7bd-115">Old behavior</span></span>

<span data-ttu-id="9e7bd-116">已弃用的包和 npm 模块旨在将 ASP.NET Core 与各种单页应用 (SPA) 框架集成。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-116">The deprecated packages and npm modules were intended to integrate ASP.NET Core with various Single-Page App (SPA) frameworks.</span></span> <span data-ttu-id="9e7bd-117">此类框架包括 Angular、React 和 React Redux。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-117">Such frameworks include Angular, React, and React with Redux.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9e7bd-118">新行为</span><span class="sxs-lookup"><span data-stu-id="9e7bd-118">New behavior</span></span>

<span data-ttu-id="9e7bd-119">[Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet 包中存在新的集成机制。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-119">A new integration mechanism exists in the [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet package.</span></span> <span data-ttu-id="9e7bd-120">自 ASP.NET Core 2.1 起，包仍然是 Angular 和 React 项目模板的基础。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-120">The package remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9e7bd-121">更改原因</span><span class="sxs-lookup"><span data-stu-id="9e7bd-121">Reason for change</span></span>

<span data-ttu-id="9e7bd-122">ASP.NET Core 支持与各种单页应用 (SPA) 框架（包括 Angular、React 和 React Redux）集成。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-122">ASP.NET Core supports integration with various Single-Page App (SPA) frameworks, including Angular, React, and React with Redux.</span></span> <span data-ttu-id="9e7bd-123">最初，与这些框架的集成是通过 ASP.NET Core 特定组件实现的，这些组件用于处理服务器端预呈现和与 Webpack 集成等情况。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-123">Initially, integration with these frameworks was accomplished with ASP.NET Core-specific components that handled scenarios like server-side prerendering and integration with Webpack.</span></span> <span data-ttu-id="9e7bd-124">随着时间的推移，行业标准也发生了变化。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-124">As time went on, industry standards changed.</span></span> <span data-ttu-id="9e7bd-125">每个 SPA 框架都发布了其自己的标准命令行接口。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-125">Each of the SPA frameworks released their own standard command-line interfaces.</span></span> <span data-ttu-id="9e7bd-126">例如，Angular CLI 和 create-react-app。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-126">For example, Angular CLI and create-react-app.</span></span>

<span data-ttu-id="9e7bd-127">当 ASP.NET Core 2.1 于 2018 年 5 月发布时，团队对标准的变化做出了响应。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-127">When ASP.NET Core 2.1 was released in May 2018, the team responded to the change in standards.</span></span> <span data-ttu-id="9e7bd-128">提供了一种更新且更简单的方法来与 SPA 框架自身的工具链集成。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-128">A newer and simpler way to integrate with the SPA frameworks' own toolchains was provided.</span></span> <span data-ttu-id="9e7bd-129">自 ASP.NET Core 2.1 起，包 `Microsoft.AspNetCore.SpaServices.Extensions` 中存在新的集成机制，且仍是 Angular 和 React 项目模板的基础。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-129">The new integration mechanism exists in the package `Microsoft.AspNetCore.SpaServices.Extensions` and remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

<span data-ttu-id="9e7bd-130">为了阐明较低版本的 ASP.NET Core 特定组件不相关且不建议使用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e7bd-130">To clarify that the older ASP.NET Core-specific components are irrelevant and not recommended:</span></span>

- <span data-ttu-id="9e7bd-131">2\.1 之前的集成机制被标记为已过时。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-131">The pre-2.1 integration mechanism is marked as obsolete.</span></span>
- <span data-ttu-id="9e7bd-132">支持 npm 包被标记为已弃用。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-132">The supporting npm packages are marked as deprecated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9e7bd-133">建议操作</span><span class="sxs-lookup"><span data-stu-id="9e7bd-133">Recommended action</span></span>

<span data-ttu-id="9e7bd-134">如果正在使用这些包，请更新应用以使用以下功能：</span><span class="sxs-lookup"><span data-stu-id="9e7bd-134">If you're using these packages, update your apps to use the functionality:</span></span>

- <span data-ttu-id="9e7bd-135">在 `Microsoft.AspNetCore.SpaServices.Extensions` 包中。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-135">In the `Microsoft.AspNetCore.SpaServices.Extensions` package.</span></span>
- <span data-ttu-id="9e7bd-136">由使用的 SPA 框架提供</span><span class="sxs-lookup"><span data-stu-id="9e7bd-136">Provided by the SPA frameworks you're using</span></span>

<span data-ttu-id="9e7bd-137">若要启用服务器端预呈现和热模块重载等功能，请参阅相应的 SPA 框架的文档。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-137">To enable features like server-side prerendering and hot module reload, see the documentation for the corresponding SPA framework.</span></span> <span data-ttu-id="9e7bd-138">`Microsoft.AspNetCore.SpaServices.Extensions` 中的功能未  过时，将继续受到支持。</span><span class="sxs-lookup"><span data-stu-id="9e7bd-138">The functionality in `Microsoft.AspNetCore.SpaServices.Extensions` is *not* obsolete and will continue to be supported.</span></span>

#### <a name="category"></a><span data-ttu-id="9e7bd-139">类别</span><span class="sxs-lookup"><span data-stu-id="9e7bd-139">Category</span></span>

<span data-ttu-id="9e7bd-140">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9e7bd-140">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9e7bd-141">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9e7bd-141">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
