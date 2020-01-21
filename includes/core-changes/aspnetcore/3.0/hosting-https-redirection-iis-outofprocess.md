---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937304"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a><span data-ttu-id="7a2a8-101">托管：已为 IIS 进程外应用启用 HTTPS 重定向</span><span class="sxs-lookup"><span data-stu-id="7a2a8-101">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>

<span data-ttu-id="7a2a8-102">用于通过 IIS 进程外应用进行托管的 [ASP.NET Core 模块 (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) 的 13.0.19218.0 版本可为 ASP.NET Core 3.0 和 2.2 应用启用现有 HTTPS 重定向功能。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-102">Version 13.0.19218.0 of the [ASP.NET Core Module (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) for hosting via IIS out-of-process enables an existing HTTPS redirection feature for ASP.NET Core 3.0 and 2.2 apps.</span></span>

<span data-ttu-id="7a2a8-103">有关讨论，请参阅 [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243)。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-103">For discussion, see [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7a2a8-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="7a2a8-104">Version introduced</span></span>

<span data-ttu-id="7a2a8-105">3.0</span><span class="sxs-lookup"><span data-stu-id="7a2a8-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7a2a8-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="7a2a8-106">Old behavior</span></span>

<span data-ttu-id="7a2a8-107">ASP.NET Core 2.1 项目模板首先引入了对 HTTPS 中间件方法的支持，例如 <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> 和 <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-107">The ASP.NET Core 2.1 project template first introduced support for HTTPS middleware methods like <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> and <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>.</span></span> <span data-ttu-id="7a2a8-108">启用 HTTPS 重定向需要添加配置，因为开发中的应用不使用默认端口 443。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-108">Enabling HTTPS redirection required the addition of configuration, since apps in development don't use the default port of 443.</span></span> <span data-ttu-id="7a2a8-109">仅当请求已使用 HTTPS 时，[HTTP 严格传输安全 (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) 才处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-109">[HTTP Strict Transport Security (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) is active only if the request is already using HTTPS.</span></span> <span data-ttu-id="7a2a8-110">默认跳过 localhost。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-110">Localhost is skipped by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7a2a8-111">新行为</span><span class="sxs-lookup"><span data-stu-id="7a2a8-111">New behavior</span></span>

<span data-ttu-id="7a2a8-112">在 ASP.NET Core 3.0 中，IIS HTTPS 方案[已增强](https://github.com/dotnet/AspNetCore/pull/4685)。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-112">In ASP.NET Core 3.0, the IIS HTTPS scenario was [enhanced](https://github.com/dotnet/AspNetCore/pull/4685).</span></span> <span data-ttu-id="7a2a8-113">利用此增强功能，应用可以发现服务器的 HTTPS 端口并默认使 `UseHttpsRedirection` 工作。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-113">With the enhancement, an app could discover the server's HTTPS ports and make `UseHttpsRedirection` work by default.</span></span> <span data-ttu-id="7a2a8-114">进程内组件通过 `IServerAddresses` 功能完成端口发现，该功能仅影响 ASP.NET Core 3.0 应用，因为进程内库通过框架进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-114">The in-process component accomplished port discovery with the `IServerAddresses` feature, which only affects ASP.NET Core 3.0 apps because the in-process library is versioned with the framework.</span></span> <span data-ttu-id="7a2a8-115">进程外组件已更改为自动添加 `ASPNETCORE_HTTPS_PORT` 环境变量。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-115">The out-of-process component changed to automatically add the `ASPNETCORE_HTTPS_PORT` environment variable.</span></span> <span data-ttu-id="7a2a8-116">由于进程外组件是全局共享组件，因此此更改会同时影响 ASP.NET Core 2.2 和 3.0 应用。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-116">This change affected both ASP.NET Core 2.2 and 3.0 apps because the out-of-process component is shared globally.</span></span> <span data-ttu-id="7a2a8-117">ASP.NET Core 2.1 应用不会受到影响，因为它们默认使用 ANCM 的先前版本。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-117">ASP.NET Core 2.1 apps aren't affected because they use a prior version of ANCM by default.</span></span>

<span data-ttu-id="7a2a8-118">前面的行为已在 ASP.NET Core 3.0.1 和 3.1.0 预览版 3 中进行修改，以反转 ASP.NET Core 2.x 中的行为更改。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-118">The preceding behavior was modified in ASP.NET Core 3.0.1 and 3.1.0 Preview 3 to reverse the behavior changes in ASP.NET Core 2.x.</span></span> <span data-ttu-id="7a2a8-119">这些更改仅影响 IIS 进程外应用。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-119">These changes only affect IIS out-of-process apps.</span></span>

<span data-ttu-id="7a2a8-120">如上所述，安装 ASP.NET Core 3.0.0 还具有在 ASP.NET Core 2.x 应用中激活 `UseHttpsRedirection` 中间件的副作用。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-120">As detailed above, installing ASP.NET Core 3.0.0 had the side effect of also activating the `UseHttpsRedirection` middleware in ASP.NET Core 2.x apps.</span></span> <span data-ttu-id="7a2a8-121">已对 ASP.NET Core 3.0.1 和 3.1.0 预览版 3 中的 ANCM 进行更改，以确保安装它们时不会再对 ASP.NET Core 2.x 应用产生此影响。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-121">A change was made to ANCM in ASP.NET Core 3.0.1 and 3.1.0 Preview 3 such that installing them no longer has this effect on ASP.NET Core 2.x apps.</span></span> <span data-ttu-id="7a2a8-122">ANCM 在 ASP.NET Core 3.0.0 中填充的 `ASPNETCORE_HTTPS_PORT` 环境变量在 ASP.NET Core 3.0.1 和 3.1.0 预览版 3 中已更改为 `ASPNETCORE_ANCM_HTTPS_PORT`。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-122">The `ASPNETCORE_HTTPS_PORT` environment variable that ANCM populated in ASP.NET Core 3.0.0 was changed to `ASPNETCORE_ANCM_HTTPS_PORT` in ASP.NET Core 3.0.1 and 3.1.0 Preview 3.</span></span> <span data-ttu-id="7a2a8-123">`UseHttpsRedirection` 在这些版本中也已更新，可同时理解新旧变量。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-123">`UseHttpsRedirection` was also updated in these releases to understand both the new and old variables.</span></span> <span data-ttu-id="7a2a8-124">不会更新 ASP.NET Core 2.x。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-124">ASP.NET Core 2.x won't be updated.</span></span> <span data-ttu-id="7a2a8-125">因此，它会还原为默认禁用的先前行为。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-125">As a result, it reverts to the previous behavior of being disabled by default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7a2a8-126">更改原因</span><span class="sxs-lookup"><span data-stu-id="7a2a8-126">Reason for change</span></span>

<span data-ttu-id="7a2a8-127">已改进 ASP.NET Core 3.0 功能。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-127">Improved ASP.NET Core 3.0 functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7a2a8-128">建议操作</span><span class="sxs-lookup"><span data-stu-id="7a2a8-128">Recommended action</span></span>

<span data-ttu-id="7a2a8-129">如果希望所有客户端都使用 HTTPS，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-129">No action is required if you want all clients to use HTTPS.</span></span> <span data-ttu-id="7a2a8-130">要允许部分客户端使用 HTTP，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="7a2a8-130">To allow some clients to use HTTP, take one of the following steps:</span></span>

* <span data-ttu-id="7a2a8-131">从项目的 `Startup.Configure` 方法中删除对 `UseHttpsRedirection` 和 `UseHsts` 的调用，然后重新部署应用。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-131">Remove the calls to `UseHttpsRedirection` and `UseHsts` from your project's `Startup.Configure` method, and redeploy the app.</span></span>
* <span data-ttu-id="7a2a8-132">在 web.config 文件中，将 `ASPNETCORE_HTTPS_PORT` 环境变量设置为空字符串  。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-132">In your *web.config* file, set the `ASPNETCORE_HTTPS_PORT` environment variable to an empty string.</span></span> <span data-ttu-id="7a2a8-133">无需重新部署应用即可直接在服务器上进行此更改。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-133">This change can occur directly on the server without redeploying the app.</span></span> <span data-ttu-id="7a2a8-134">例如：</span><span class="sxs-lookup"><span data-stu-id="7a2a8-134">For example:</span></span>

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

<span data-ttu-id="7a2a8-135">`UseHttpsRedirection` 仍可：</span><span class="sxs-lookup"><span data-stu-id="7a2a8-135">`UseHttpsRedirection` can still be:</span></span>

* <span data-ttu-id="7a2a8-136">在 ASP.NET Core 2.x 中手动激活，方法是将 `ASPNETCORE_HTTPS_PORT` 环境变量设置为相应的端口号（在大多数生产方案中为 443）。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-136">Activated manually in ASP.NET Core 2.x by setting the `ASPNETCORE_HTTPS_PORT` environment variable to the appropriate port number (443 in most production scenarios).</span></span>
* <span data-ttu-id="7a2a8-137">在 ASP.NET Core 3.x 中停用，方法是使用空字符串值定义 `ASPNETCORE_ANCM_HTTPS_PORT`。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-137">Deactivated in ASP.NET Core 3.x by defining `ASPNETCORE_ANCM_HTTPS_PORT` with an empty string value.</span></span> <span data-ttu-id="7a2a8-138">此值的设置方式与前面的 `ASPNETCORE_HTTPS_PORT` 示例相同。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-138">This value is set in the same fashion as the preceding `ASPNETCORE_HTTPS_PORT` example.</span></span>

<span data-ttu-id="7a2a8-139">运行 ASP.NET Core 3.0.0 应用的计算机应先安装 ASP.NET Core 3.0.1 运行时，然后再安装 ASP.NET Core 3.1.0 预览版 3 ANCM。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-139">Machines running ASP.NET Core 3.0.0 apps should install the ASP.NET Core 3.0.1 runtime before installing the ASP.NET Core 3.1.0 Preview 3 ANCM.</span></span> <span data-ttu-id="7a2a8-140">这样做可以确保继续按预期对 ASP.NET Core 3.0 应用运行 `UseHttpsRedirection`。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-140">Doing so ensures that `UseHttpsRedirection` continues to operate as expected for the ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="7a2a8-141">在 Azure 应用服务中，由于 ANCM 具有全局性，其部署时间与运行时不同。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-141">In Azure App Service, ANCM deploys on a separate schedule from the runtime because of its global nature.</span></span> <span data-ttu-id="7a2a8-142">部署 ASP.NET Core 3.0.1 和 3.1.0 后，才会将 ANCM 以及相应的更改部署到 Azure。</span><span class="sxs-lookup"><span data-stu-id="7a2a8-142">ANCM was deployed to Azure with these changes after ASP.NET Core 3.0.1 and 3.1.0 were deployed.</span></span>

#### <a name="category"></a><span data-ttu-id="7a2a8-143">类别</span><span class="sxs-lookup"><span data-stu-id="7a2a8-143">Category</span></span>

<span data-ttu-id="7a2a8-144">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7a2a8-144">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7a2a8-145">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="7a2a8-145">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
