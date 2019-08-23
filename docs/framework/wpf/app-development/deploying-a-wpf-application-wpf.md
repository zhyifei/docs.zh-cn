---
title: 部署 WPF 应用程序 (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: cfb617fde514c93596d52b0ca70da39c6e5be301
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958646"
---
# <a name="deploying-a-wpf-application-wpf"></a><span data-ttu-id="78baa-102">部署 WPF 应用程序 (WPF)</span><span class="sxs-lookup"><span data-stu-id="78baa-102">Deploying a WPF Application (WPF)</span></span>
<span data-ttu-id="78baa-103">生成 Windows Presentation Foundation (WPF) 应用程序后, 需要部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-103">After Windows Presentation Foundation (WPF) applications are built, they need to be deployed.</span></span> <span data-ttu-id="78baa-104">Windows 和 .NET Framework 包括几种部署技术。</span><span class="sxs-lookup"><span data-stu-id="78baa-104">Windows and the .NET Framework include several deployment technologies.</span></span> <span data-ttu-id="78baa-105">用于部署 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序的部署技术取决于应用程序的类型。</span><span class="sxs-lookup"><span data-stu-id="78baa-105">The deployment technology that is used to deploy a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application depends on the application type.</span></span> <span data-ttu-id="78baa-106">本主题将简要概述各项部署技术，以及如何使用这些技术来满足各类 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序的部署要求。</span><span class="sxs-lookup"><span data-stu-id="78baa-106">This topic provides a brief overview of each deployment technology, and how they are used in conjunction with the deployment requirements of each [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application type.</span></span>  

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a><span data-ttu-id="78baa-107">部署技术</span><span class="sxs-lookup"><span data-stu-id="78baa-107">Deployment Technologies</span></span>  
 <span data-ttu-id="78baa-108">Windows 和 .NET Framework 包括几种部署技术, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="78baa-108">Windows and the .NET Framework include several deployment technologies, including:</span></span>  
  
- <span data-ttu-id="78baa-109">XCopy 部署。</span><span class="sxs-lookup"><span data-stu-id="78baa-109">XCopy deployment.</span></span>  
  
- [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] <span data-ttu-id="78baa-110">部署。</span><span class="sxs-lookup"><span data-stu-id="78baa-110">deployment.</span></span>  
  
- <span data-ttu-id="78baa-111">ClickOnce 部署。</span><span class="sxs-lookup"><span data-stu-id="78baa-111">ClickOnce deployment.</span></span>  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a><span data-ttu-id="78baa-112">XCopy 部署</span><span class="sxs-lookup"><span data-stu-id="78baa-112">XCopy Deployment</span></span>  
 <span data-ttu-id="78baa-113">XCopy 部署是指使用 XCopy 命令行程序将文件从一个位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="78baa-113">XCopy deployment refers to the use of the XCopy command-line program to copy files from one location to another.</span></span> <span data-ttu-id="78baa-114">XCopy 部署适用于下列情况：</span><span class="sxs-lookup"><span data-stu-id="78baa-114">XCopy deployment is suitable under the following circumstances:</span></span>  
  
- <span data-ttu-id="78baa-115">应用程序是自包含的。</span><span class="sxs-lookup"><span data-stu-id="78baa-115">The application is self-contained.</span></span> <span data-ttu-id="78baa-116">无需更新客户端，即可运行。</span><span class="sxs-lookup"><span data-stu-id="78baa-116">It does not need to update the client to run.</span></span>  
  
- <span data-ttu-id="78baa-117">应用程序文件必须从一个位置移到另一个位置，如从生成位置（本地磁盘、[!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] 文件共享等）移到发布位置（网站、[!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] 文件共享等）。</span><span class="sxs-lookup"><span data-stu-id="78baa-117">Application files must be moved from one location to another, such as from a build location (local disk, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] file share, and so on) to a publish location (Web site, [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] file share, and so on).</span></span>  
  
- <span data-ttu-id="78baa-118">应用程序无需进行 Shell 集成（“开始”菜单快捷方式、桌面图标等）。</span><span class="sxs-lookup"><span data-stu-id="78baa-118">The application does not require shell integration (Start menu shortcut, desktop icon, and so on).</span></span>  
  
 <span data-ttu-id="78baa-119">XCopy 适用于简单的部署方案；如果需要更为复杂的部署功能，则会限制使用 XCopy。</span><span class="sxs-lookup"><span data-stu-id="78baa-119">Although XCopy is suitable for simple deployment scenarios, it is limited when more complex deployment capabilities are required.</span></span> <span data-ttu-id="78baa-120">具体而言就是，使用 XCopy 往往会导致创建、执行并维护能以可靠方式管理部署的脚本，并进而产生相应的开销。</span><span class="sxs-lookup"><span data-stu-id="78baa-120">In particular, using XCopy often incurs the overhead for creating, executing, and maintaining scripts for managing deployment in a robust way.</span></span> <span data-ttu-id="78baa-121">此外，XCopy 不支持版本控制、卸载或回滚。</span><span class="sxs-lookup"><span data-stu-id="78baa-121">Furthermore, XCopy does not support versioning, uninstallation, or rollback.</span></span>  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a><span data-ttu-id="78baa-122">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="78baa-122">Windows Installer</span></span>  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] <span data-ttu-id="78baa-123">允许应用程序打包为可轻松分发到客户端并运行的自包含可执行文件。</span><span class="sxs-lookup"><span data-stu-id="78baa-123">allows applications to be packaged as self-contained executables that can be easily distributed to clients and run.</span></span> <span data-ttu-id="78baa-124">此外, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]还随 Windows 一起安装, 并允许与桌面、"开始" 菜单和 "程序" 控制面板集成。</span><span class="sxs-lookup"><span data-stu-id="78baa-124">Furthermore, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] is installed with Windows and enables integration with the desktop, the Start menu, and the Programs control panel.</span></span>  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] <span data-ttu-id="78baa-125">简化了应用程序的安装和卸载，但它不会提供相应工具以确保已安装的应用程序始终为最新版本。</span><span class="sxs-lookup"><span data-stu-id="78baa-125">simplifies the installation and uninstallation of applications, but it does not provide facilities for ensuring that installed applications are kept up-to-date from a versioning standpoint.</span></span>  
  
 <span data-ttu-id="78baa-126">有关 Windows Installer 的详细信息, 请参阅[Windows Installer 部署](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。</span><span class="sxs-lookup"><span data-stu-id="78baa-126">For more information about Windows Installer, see [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a><span data-ttu-id="78baa-127">ClickOnce 部署</span><span class="sxs-lookup"><span data-stu-id="78baa-127">ClickOnce Deployment</span></span>  
 <span data-ttu-id="78baa-128">ClickOnce 为非 Web 应用程序启用 Web 样式应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="78baa-128">ClickOnce enables Web-style application deployment for non-Web applications.</span></span> <span data-ttu-id="78baa-129">应用程序会发布到 Web 或文件服务器，也会从 Web 或文件服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="78baa-129">Applications are published to and deployed from Web or file servers.</span></span> <span data-ttu-id="78baa-130">尽管 ClickOnce 不支持安装的应用程序所支持的所有[!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]客户端功能, 但它支持的子集包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="78baa-130">Although ClickOnce does not support the full range of client features that [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]-installed applications do, it does support a subset that includes the following:</span></span>  
  
- <span data-ttu-id="78baa-131">与“开始”菜单及“程序”控制面板集成。</span><span class="sxs-lookup"><span data-stu-id="78baa-131">Integration with the Start menu and Programs control panel.</span></span>  
  
- <span data-ttu-id="78baa-132">版本控制、回滚和卸载。</span><span class="sxs-lookup"><span data-stu-id="78baa-132">Versioning, rollback, and uninstallation.</span></span>  
  
- <span data-ttu-id="78baa-133">联机安装模式，该模式始终会从部署位置启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-133">Online install mode, which always launches an application from the deployment location.</span></span>  
  
- <span data-ttu-id="78baa-134">当有新版本发布时自动更新。</span><span class="sxs-lookup"><span data-stu-id="78baa-134">Automatic updating when new versions are released.</span></span>  
  
- <span data-ttu-id="78baa-135">注册文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="78baa-135">Registration of file extensions.</span></span>  
  
 <span data-ttu-id="78baa-136">有关 ClickOnce 的详细信息, 请参阅[Clickonce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。</span><span class="sxs-lookup"><span data-stu-id="78baa-136">For more information about ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a><span data-ttu-id="78baa-137">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="78baa-137">Deploying WPF Applications</span></span>  
 <span data-ttu-id="78baa-138">适用于 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序的部署选项取决于应用程序的类型。</span><span class="sxs-lookup"><span data-stu-id="78baa-138">The deployment options for a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application depend on the type of application.</span></span> <span data-ttu-id="78baa-139">从部署的角度来看，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 共有三种重要的应用程序类型：</span><span class="sxs-lookup"><span data-stu-id="78baa-139">From a deployment perspective, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] has three significant application types:</span></span>  
  
- <span data-ttu-id="78baa-140">独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-140">Standalone applications.</span></span>  
  
- <span data-ttu-id="78baa-141">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-141">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications.</span></span>  
  
- [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="78baa-142">。</span><span class="sxs-lookup"><span data-stu-id="78baa-142">.</span></span>  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a><span data-ttu-id="78baa-143">部署独立应用程序</span><span class="sxs-lookup"><span data-stu-id="78baa-143">Deploying Standalone Applications</span></span>  
 <span data-ttu-id="78baa-144">使用 ClickOnce 或[!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]部署独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-144">Standalone applications are deployed using either ClickOnce or [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].</span></span> <span data-ttu-id="78baa-145">无论使用哪一项，独立应用程序都要在完全信任的状态下才能运行。</span><span class="sxs-lookup"><span data-stu-id="78baa-145">Either way, standalone applications require full trust to run.</span></span> <span data-ttu-id="78baa-146">使用 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 部署的独立应用程序会被自动授予完全信任状态。</span><span class="sxs-lookup"><span data-stu-id="78baa-146">Full trust is automatically granted to standalone applications that are deployed using [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].</span></span> <span data-ttu-id="78baa-147">使用 ClickOnce 部署的独立应用程序不会自动被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="78baa-147">Standalone applications that are deployed using ClickOnce are not automatically granted full trust.</span></span> <span data-ttu-id="78baa-148">相反, ClickOnce 会显示一个安全警告对话框, 用户必须先接受该对话框, 然后才能安装独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-148">Instead, ClickOnce displays a security warning dialog that users must accept before a standalone application is installed.</span></span> <span data-ttu-id="78baa-149">如果接受，独立应用程序就会安装并被授予完全信任状态。</span><span class="sxs-lookup"><span data-stu-id="78baa-149">If accepted, the standalone application is installed and granted full trust.</span></span> <span data-ttu-id="78baa-150">如果不接受，则独立应用程序不会安装。</span><span class="sxs-lookup"><span data-stu-id="78baa-150">If not, the standalone application is not installed.</span></span>  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a><span data-ttu-id="78baa-151">部署仅标记 XAML 应用程序</span><span class="sxs-lookup"><span data-stu-id="78baa-151">Deploying Markup-Only XAML Applications</span></span>  
 <span data-ttu-id="78baa-152">仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记页面通常会发布到 Web 服务器 (如 HTML 页面), 可以使用 Internet Explorer 来查看。</span><span class="sxs-lookup"><span data-stu-id="78baa-152">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are usually published to Web servers, like HTML pages, and can be viewed using Internet Explorer.</span></span> <span data-ttu-id="78baa-153">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面会按照 Internet 区域权限集定义的限制，在部分信任的安全沙箱内运行。</span><span class="sxs-lookup"><span data-stu-id="78baa-153">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages run within a partial-trust security sandbox with restrictions that are defined by the Internet zone permission set.</span></span> <span data-ttu-id="78baa-154">这为基于 HTML 的 Web 应用程序提供了等效的安全沙箱。</span><span class="sxs-lookup"><span data-stu-id="78baa-154">This provides an equivalent security sandbox to HTML-based Web applications.</span></span>  
  
 <span data-ttu-id="78baa-155">有关 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序安全性的详细信息，请参阅[安全性](../security-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="78baa-155">For more information about security for [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications, see [Security](../security-wpf.md).</span></span>  
  
 <span data-ttu-id="78baa-156">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面可以利用 XCopy 或 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 安装到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="78baa-156">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages can be installed to the local file system by using either XCopy or [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].</span></span> <span data-ttu-id="78baa-157">可以使用 Internet Explorer 或 Windows 资源管理器查看这些页面。</span><span class="sxs-lookup"><span data-stu-id="78baa-157">These pages can be viewed using Internet Explorer or Windows Explorer.</span></span>  
  
 <span data-ttu-id="78baa-158">有关 XAML 的详细信息，请参阅 [XAML 概述 (WPF)](../advanced/xaml-overview-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="78baa-158">For more information about XAML, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a><span data-ttu-id="78baa-159">部署 XAML 浏览器应用程序</span><span class="sxs-lookup"><span data-stu-id="78baa-159">Deploying XAML Browser Applications</span></span>  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] <span data-ttu-id="78baa-160">是需要部署以下三个文件的编译型应用程序：</span><span class="sxs-lookup"><span data-stu-id="78baa-160">are compiled applications that require the following three files to be deployed:</span></span>  
  
- <span data-ttu-id="78baa-161">*ApplicationName*:可执行程序集应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="78baa-161">*ApplicationName*.exe: The executable assembly application file.</span></span>  
  
- <span data-ttu-id="78baa-162">*ApplicationName*:部署清单。</span><span class="sxs-lookup"><span data-stu-id="78baa-162">*ApplicationName*.xbap: The deployment manifest.</span></span>  
  
- <span data-ttu-id="78baa-163">*ApplicationName*.manifest:应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="78baa-163">*ApplicationName*.exe.manifest: The application manifest.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78baa-164">有关部署和应用程序清单的详细信息，请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="78baa-164">For more information about deployment and application manifests, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="78baa-165">这些文件在 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 生成时产生。</span><span class="sxs-lookup"><span data-stu-id="78baa-165">These files are produced when an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is built.</span></span> <span data-ttu-id="78baa-166">有关详细信息，请参阅[如何：创建新的 WPF 浏览器应用](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))程序项目。</span><span class="sxs-lookup"><span data-stu-id="78baa-166">For more information, see [How to: Create a New WPF Browser Application Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).</span></span> <span data-ttu-id="78baa-167">与仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记页面一样, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]通常会发布到 Web 服务器, 并使用 Internet Explorer 进行查看。</span><span class="sxs-lookup"><span data-stu-id="78baa-167">Like markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] are typically published to a Web server and viewed using Internet Explorer.</span></span>  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] <span data-ttu-id="78baa-168">可以使用任意部署技术部署到客户端。</span><span class="sxs-lookup"><span data-stu-id="78baa-168">can be deployed to clients using any of the deployment techniques.</span></span> <span data-ttu-id="78baa-169">但建议使用 ClickOnce, 因为它提供以下功能:</span><span class="sxs-lookup"><span data-stu-id="78baa-169">However, ClickOnce is recommended since it provides the following capabilities:</span></span>  
  
1. <span data-ttu-id="78baa-170">当有新版本发布时自动更新。</span><span class="sxs-lookup"><span data-stu-id="78baa-170">Automatic updates when a new version is published.</span></span>  
  
2. <span data-ttu-id="78baa-171">适用于在完全信任状态下运行的 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 的提升权限。</span><span class="sxs-lookup"><span data-stu-id="78baa-171">Elevation privileges for the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] running with full trust.</span></span>  
  
 <span data-ttu-id="78baa-172">默认情况下，ClickOnce 会使用.deploy 扩展名来发布应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="78baa-172">By default, ClickOnce publishes application files with the .deploy extension.</span></span> <span data-ttu-id="78baa-173">这可能会引发问题，但可被禁用。</span><span class="sxs-lookup"><span data-stu-id="78baa-173">This can be problematic, but can be disabled.</span></span> <span data-ttu-id="78baa-174">有关详细信息，请参阅 [ClickOnce 部署中的服务器和客户端配置问题](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)。</span><span class="sxs-lookup"><span data-stu-id="78baa-174">For more information, see [Server and Client Configuration Issues in ClickOnce Deployments](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).</span></span>  
  
 <span data-ttu-id="78baa-175">有关部署 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 的详细信息，请参阅 [WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="78baa-175">For more information about deploying [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a><span data-ttu-id="78baa-176">安装 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78baa-176">Installing the .NET Framework</span></span>  
 <span data-ttu-id="78baa-177">若要运行[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序, Microsoft .NET 框架必须安装在客户端上。</span><span class="sxs-lookup"><span data-stu-id="78baa-177">To run a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, the Microsoft .NET Framework must be installed on the client.</span></span> <span data-ttu-id="78baa-178">查看浏览器承载的应用程序时[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , Internet Explorer 会自动检测是否随 .NET Framework 一起安装了客户端。</span><span class="sxs-lookup"><span data-stu-id="78baa-178">Internet Explorer automatically detects whether clients are installed with .NET Framework when [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] browser-hosted applications are viewed.</span></span> <span data-ttu-id="78baa-179">如果未安装 .NET Framework, Internet Explorer 将提示用户安装。</span><span class="sxs-lookup"><span data-stu-id="78baa-179">If the .NET Framework is not installed, Internet Explorer prompts users to install it.</span></span>  
  
 <span data-ttu-id="78baa-180">为了检测 .NET Framework 是否已安装, Internet Explorer 包括一个引导程序应用程序, 该应用程序已注册为具有以下扩展名的内容文件的后备多用途 Internet 邮件扩展 (MIME) 处理程序: .xaml、.xps、xbap、和。</span><span class="sxs-lookup"><span data-stu-id="78baa-180">To detect whether the .NET Framework is installed, Internet Explorer includes a bootstrapper application that is registered as the fallback Multipurpose Internet Mail Extensions (MIME) handler for content files with the following extensions: .xaml, .xps, .xbap, and .application.</span></span> <span data-ttu-id="78baa-181">如果你导航到这些文件类型, 并且客户端上未安装 .NET Framework, 则引导程序应用程序会请求安装它的权限。</span><span class="sxs-lookup"><span data-stu-id="78baa-181">If you navigate to these file types and the .NET Framework is not installed on the client, the bootstrapper application requests permission to install it.</span></span> <span data-ttu-id="78baa-182">如果未提供权限, 则不会安装 .NET Framework 和应用程序。</span><span class="sxs-lookup"><span data-stu-id="78baa-182">If permission is not provided, neither the .NET Framework nor the application is installed.</span></span>  
  
 <span data-ttu-id="78baa-183">如果授予了权限, Internet Explorer 将使用 Microsoft 后台智能传输服务 (BITS) 下载并安装 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="78baa-183">If permission is granted, Internet Explorer downloads and installs the .NET Framework using the Microsoft Background Intelligent Transfer Service (BITS).</span></span> <span data-ttu-id="78baa-184">成功安装 .NET Framework 后, 最初请求的文件将在新的浏览器窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="78baa-184">After successful installation of the .NET Framework, the originally requested file is opened in a new browser window.</span></span>  
  
 <span data-ttu-id="78baa-185">有关详细信息，请参阅[部署 .NET Framework 和应用程序](../../deployment/index.md)。</span><span class="sxs-lookup"><span data-stu-id="78baa-185">For more information, see [Deploying the .NET Framework and Applications](../../deployment/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78baa-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="78baa-186">See also</span></span>

- [<span data-ttu-id="78baa-187">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="78baa-187">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
- [<span data-ttu-id="78baa-188">安全性</span><span class="sxs-lookup"><span data-stu-id="78baa-188">Security</span></span>](../security-wpf.md)
