---
title: 部署应用
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 54d14503a0f65bb50f2dfb14d40af3b47d51589c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186316"
---
# <a name="deploy-a-wpf-application"></a><span data-ttu-id="403b5-102">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="403b5-102">Deploy a WPF Application</span></span>

<span data-ttu-id="403b5-103">构建 Windows 演示基础 （WPF） 应用程序后，需要部署它们。</span><span class="sxs-lookup"><span data-stu-id="403b5-103">After Windows Presentation Foundation (WPF) applications are built, they need to be deployed.</span></span> <span data-ttu-id="403b5-104">Windows 和 .NET 框架包括多种部署技术。</span><span class="sxs-lookup"><span data-stu-id="403b5-104">Windows and the .NET Framework include several deployment technologies.</span></span> <span data-ttu-id="403b5-105">用于部署 WPF 应用程序的部署技术取决于应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="403b5-105">The deployment technology that is used to deploy a WPF application depends on the application type.</span></span> <span data-ttu-id="403b5-106">本主题简要概述了每种部署技术，以及如何结合每种 WPF 应用程序类型的部署要求使用。</span><span class="sxs-lookup"><span data-stu-id="403b5-106">This topic provides a brief overview of each deployment technology, and how they are used in conjunction with the deployment requirements of each WPF application type.</span></span>

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a><span data-ttu-id="403b5-107">部署技术</span><span class="sxs-lookup"><span data-stu-id="403b5-107">Deployment Technologies</span></span>  
 <span data-ttu-id="403b5-108">Windows 和 .NET 框架包括多种部署技术，包括：</span><span class="sxs-lookup"><span data-stu-id="403b5-108">Windows and the .NET Framework include several deployment technologies, including:</span></span>  
  
- <span data-ttu-id="403b5-109">XCopy 部署。</span><span class="sxs-lookup"><span data-stu-id="403b5-109">XCopy deployment.</span></span>  
  
- <span data-ttu-id="403b5-110">Windows 安装程序部署。</span><span class="sxs-lookup"><span data-stu-id="403b5-110">Windows Installer deployment.</span></span>  
  
- <span data-ttu-id="403b5-111">ClickOnce 部署。</span><span class="sxs-lookup"><span data-stu-id="403b5-111">ClickOnce deployment.</span></span>  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a><span data-ttu-id="403b5-112">XCopy 部署</span><span class="sxs-lookup"><span data-stu-id="403b5-112">XCopy Deployment</span></span>  
 <span data-ttu-id="403b5-113">XCopy 部署是指使用 XCopy 命令行程序将文件从一个位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="403b5-113">XCopy deployment refers to the use of the XCopy command-line program to copy files from one location to another.</span></span> <span data-ttu-id="403b5-114">XCopy 部署适用于下列情况：</span><span class="sxs-lookup"><span data-stu-id="403b5-114">XCopy deployment is suitable under the following circumstances:</span></span>  
  
- <span data-ttu-id="403b5-115">应用程序是自包含的。</span><span class="sxs-lookup"><span data-stu-id="403b5-115">The application is self-contained.</span></span> <span data-ttu-id="403b5-116">无需更新客户端，即可运行。</span><span class="sxs-lookup"><span data-stu-id="403b5-116">It does not need to update the client to run.</span></span>  
  
- <span data-ttu-id="403b5-117">应用程序文件必须从一个位置移动到另一个位置，例如从生成位置（本地磁盘、UNC 文件共享等）移动到发布位置（网站、UNC 文件共享等）。</span><span class="sxs-lookup"><span data-stu-id="403b5-117">Application files must be moved from one location to another, such as from a build location (local disk, UNC file share, and so on) to a publish location (Web site, UNC file share, and so on).</span></span>  
  
- <span data-ttu-id="403b5-118">应用程序无需进行 Shell 集成（“开始”菜单快捷方式、桌面图标等）。</span><span class="sxs-lookup"><span data-stu-id="403b5-118">The application does not require shell integration (Start menu shortcut, desktop icon, and so on).</span></span>  
  
 <span data-ttu-id="403b5-119">XCopy 适用于简单的部署方案；如果需要更为复杂的部署功能，则会限制使用 XCopy。</span><span class="sxs-lookup"><span data-stu-id="403b5-119">Although XCopy is suitable for simple deployment scenarios, it is limited when more complex deployment capabilities are required.</span></span> <span data-ttu-id="403b5-120">具体而言就是，使用 XCopy 往往会导致创建、执行并维护能以可靠方式管理部署的脚本，并进而产生相应的开销。</span><span class="sxs-lookup"><span data-stu-id="403b5-120">In particular, using XCopy often incurs the overhead for creating, executing, and maintaining scripts for managing deployment in a robust way.</span></span> <span data-ttu-id="403b5-121">此外，XCopy 不支持版本控制、卸载或回滚。</span><span class="sxs-lookup"><span data-stu-id="403b5-121">Furthermore, XCopy does not support versioning, uninstallation, or rollback.</span></span>  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a><span data-ttu-id="403b5-122">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="403b5-122">Windows Installer</span></span>  
 <span data-ttu-id="403b5-123">Windows 安装程序允许将应用程序打包为可独立执行文件，以便轻松分发到客户端并运行。</span><span class="sxs-lookup"><span data-stu-id="403b5-123">Windows Installer allows applications to be packaged as self-contained executables that can be easily distributed to clients and run.</span></span> <span data-ttu-id="403b5-124">此外，Windows 安装程序与 Windows 一起安装，并启用与桌面、"开始"菜单和程序控制面板的集成。</span><span class="sxs-lookup"><span data-stu-id="403b5-124">Furthermore, Windows Installer is installed with Windows and enables integration with the desktop, the Start menu, and the Programs control panel.</span></span>  
  
 <span data-ttu-id="403b5-125">Windows 安装程序简化了应用程序的安装和卸载，但它不提供从版本控制的角度来看确保已安装的应用程序保持最新功能。</span><span class="sxs-lookup"><span data-stu-id="403b5-125">Windows Installer simplifies the installation and uninstallation of applications, but it does not provide facilities for ensuring that installed applications are kept up-to-date from a versioning standpoint.</span></span>  
  
 <span data-ttu-id="403b5-126">有关 Windows 安装程序的详细信息，请参阅[Windows 安装程序部署](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。</span><span class="sxs-lookup"><span data-stu-id="403b5-126">For more information about Windows Installer, see [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a><span data-ttu-id="403b5-127">ClickOnce 部署</span><span class="sxs-lookup"><span data-stu-id="403b5-127">ClickOnce Deployment</span></span>  
 <span data-ttu-id="403b5-128">ClickOnce 支持针对非 Web 应用程序部署 Web 样式的应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-128">ClickOnce enables Web-style application deployment for non-Web applications.</span></span> <span data-ttu-id="403b5-129">应用程序会发布到 Web 或文件服务器，也会从 Web 或文件服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="403b5-129">Applications are published to and deployed from Web or file servers.</span></span> <span data-ttu-id="403b5-130">尽管 ClickOnce 不支持 Windows 安装程序安装的应用程序的全部客户端功能，但它确实支持包含以下内容的子集：</span><span class="sxs-lookup"><span data-stu-id="403b5-130">Although ClickOnce does not support the full range of client features that Windows Installer-installed applications do, it does support a subset that includes the following:</span></span>  
  
- <span data-ttu-id="403b5-131">与“开始”菜单及“程序”控制面板集成。</span><span class="sxs-lookup"><span data-stu-id="403b5-131">Integration with the Start menu and Programs control panel.</span></span>  
  
- <span data-ttu-id="403b5-132">版本控制、回滚和卸载。</span><span class="sxs-lookup"><span data-stu-id="403b5-132">Versioning, rollback, and uninstallation.</span></span>  
  
- <span data-ttu-id="403b5-133">联机安装模式，该模式始终会从部署位置启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-133">Online install mode, which always launches an application from the deployment location.</span></span>  
  
- <span data-ttu-id="403b5-134">当有新版本发布时自动更新。</span><span class="sxs-lookup"><span data-stu-id="403b5-134">Automatic updating when new versions are released.</span></span>  
  
- <span data-ttu-id="403b5-135">注册文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="403b5-135">Registration of file extensions.</span></span>  
  
 <span data-ttu-id="403b5-136">有关单击"一次"的详细信息，请参阅[单击"一次安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)"。</span><span class="sxs-lookup"><span data-stu-id="403b5-136">For more information about ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a><span data-ttu-id="403b5-137">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="403b5-137">Deploying WPF Applications</span></span>  
 <span data-ttu-id="403b5-138">WPF 应用程序的部署选项取决于应用程序的类型。</span><span class="sxs-lookup"><span data-stu-id="403b5-138">The deployment options for a WPF application depend on the type of application.</span></span> <span data-ttu-id="403b5-139">从部署的角度来看，WPF 有三种重要的应用程序类型：</span><span class="sxs-lookup"><span data-stu-id="403b5-139">From a deployment perspective, WPF has three significant application types:</span></span>  
  
- <span data-ttu-id="403b5-140">独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-140">Standalone applications.</span></span>  
  
- <span data-ttu-id="403b5-141">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-141">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications.</span></span>  
  
- <span data-ttu-id="403b5-142">XAML 浏览器应用程序 （XBAP）。</span><span class="sxs-lookup"><span data-stu-id="403b5-142">XAML browser applications (XBAPs).</span></span>  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a><span data-ttu-id="403b5-143">部署独立应用程序</span><span class="sxs-lookup"><span data-stu-id="403b5-143">Deploying Standalone Applications</span></span>  
 <span data-ttu-id="403b5-144">使用 ClickOnce 或 Windows 安装程序部署独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-144">Standalone applications are deployed using either ClickOnce or Windows Installer.</span></span> <span data-ttu-id="403b5-145">无论使用哪一项，独立应用程序都要在完全信任的状态下才能运行。</span><span class="sxs-lookup"><span data-stu-id="403b5-145">Either way, standalone applications require full trust to run.</span></span> <span data-ttu-id="403b5-146">完全信任将自动授予使用 Windows 安装程序部署的独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-146">Full trust is automatically granted to standalone applications that are deployed using Windows Installer.</span></span> <span data-ttu-id="403b5-147">使用 ClickOnce 部署的独立应用程序不会自动授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="403b5-147">Standalone applications that are deployed using ClickOnce are not automatically granted full trust.</span></span> <span data-ttu-id="403b5-148">相反，ClickOnce 会显示用户在安装独立应用程序之前必须接受的安全警告对话框。</span><span class="sxs-lookup"><span data-stu-id="403b5-148">Instead, ClickOnce displays a security warning dialog that users must accept before a standalone application is installed.</span></span> <span data-ttu-id="403b5-149">如果接受，独立应用程序就会安装并被授予完全信任状态。</span><span class="sxs-lookup"><span data-stu-id="403b5-149">If accepted, the standalone application is installed and granted full trust.</span></span> <span data-ttu-id="403b5-150">如果不接受，则独立应用程序不会安装。</span><span class="sxs-lookup"><span data-stu-id="403b5-150">If not, the standalone application is not installed.</span></span>  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a><span data-ttu-id="403b5-151">部署仅标记 XAML 应用程序</span><span class="sxs-lookup"><span data-stu-id="403b5-151">Deploying Markup-Only XAML Applications</span></span>  
 <span data-ttu-id="403b5-152">仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记页面通常发布到 Web 服务器（如 HTML 页面），并且可以使用 Internet Explorer 查看。</span><span class="sxs-lookup"><span data-stu-id="403b5-152">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are usually published to Web servers, like HTML pages, and can be viewed using Internet Explorer.</span></span> <span data-ttu-id="403b5-153">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面会按照 Internet 区域权限集定义的限制，在部分信任的安全沙箱内运行。</span><span class="sxs-lookup"><span data-stu-id="403b5-153">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages run within a partial-trust security sandbox with restrictions that are defined by the Internet zone permission set.</span></span> <span data-ttu-id="403b5-154">这为基于 HTML 的 Web 应用程序提供了等效的安全沙盒。</span><span class="sxs-lookup"><span data-stu-id="403b5-154">This provides an equivalent security sandbox to HTML-based Web applications.</span></span>  
  
 <span data-ttu-id="403b5-155">有关 WPF 应用程序安全性的详细信息，请参阅[安全](../security-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="403b5-155">For more information about security for WPF applications, see [Security](../security-wpf.md).</span></span>  
  
 <span data-ttu-id="403b5-156">通过使用 XCopy[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]或 Windows 安装程序，只能将标记页面安装到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="403b5-156">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages can be installed to the local file system by using either XCopy or Windows Installer.</span></span> <span data-ttu-id="403b5-157">可以使用 Internet 资源管理器或 Windows 资源管理器查看这些页面。</span><span class="sxs-lookup"><span data-stu-id="403b5-157">These pages can be viewed using Internet Explorer or Windows Explorer.</span></span>  
  
 <span data-ttu-id="403b5-158">有关 XAML 的详细信息，请参阅 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="403b5-158">For more information about XAML, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a><span data-ttu-id="403b5-159">部署 XAML 浏览器应用程序</span><span class="sxs-lookup"><span data-stu-id="403b5-159">Deploying XAML Browser Applications</span></span>  
 <span data-ttu-id="403b5-160">XBAP 是需要部署以下三个文件的编译应用程序：</span><span class="sxs-lookup"><span data-stu-id="403b5-160">XBAPs are compiled applications that require the following three files to be deployed:</span></span>  
  
- <span data-ttu-id="403b5-161">*应用程序名称*.exe：可执行的程序集应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="403b5-161">*ApplicationName*.exe: The executable assembly application file.</span></span>  
  
- <span data-ttu-id="403b5-162">*应用程序名称*.xbap：部署清单。</span><span class="sxs-lookup"><span data-stu-id="403b5-162">*ApplicationName*.xbap: The deployment manifest.</span></span>  
  
- <span data-ttu-id="403b5-163">*应用程序名称*.exe.manifest：应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="403b5-163">*ApplicationName*.exe.manifest: The application manifest.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="403b5-164">有关部署和应用程序清单的详细信息，请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="403b5-164">For more information about deployment and application manifests, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="403b5-165">这些文件是在生成 XBAP 时生成的。</span><span class="sxs-lookup"><span data-stu-id="403b5-165">These files are produced when an XBAP is built.</span></span> <span data-ttu-id="403b5-166">有关详细信息，请参阅[如何：创建新的 WPF 浏览器应用程序项目](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="403b5-166">For more information, see [How to: Create a New WPF Browser Application Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).</span></span> <span data-ttu-id="403b5-167">与仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记页面一样，XBAP 通常发布到 Web 服务器并使用 Internet 资源管理器进行查看。</span><span class="sxs-lookup"><span data-stu-id="403b5-167">Like markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages, XBAPs are typically published to a Web server and viewed using Internet Explorer.</span></span>  
  
 <span data-ttu-id="403b5-168">可以使用任何部署技术将 XBAP 部署到客户端。</span><span class="sxs-lookup"><span data-stu-id="403b5-168">XBAPs can be deployed to clients using any of the deployment techniques.</span></span> <span data-ttu-id="403b5-169">但是，建议单击一次，因为它提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="403b5-169">However, ClickOnce is recommended since it provides the following capabilities:</span></span>  
  
1. <span data-ttu-id="403b5-170">当有新版本发布时自动更新。</span><span class="sxs-lookup"><span data-stu-id="403b5-170">Automatic updates when a new version is published.</span></span>  
  
2. <span data-ttu-id="403b5-171">完全信任运行的 XBAP 的提升权限。</span><span class="sxs-lookup"><span data-stu-id="403b5-171">Elevation privileges for the XBAP running with full trust.</span></span>  
  
 <span data-ttu-id="403b5-172">默认情况下，ClickOnce 会使用.deploy 扩展名来发布应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="403b5-172">By default, ClickOnce publishes application files with the .deploy extension.</span></span> <span data-ttu-id="403b5-173">这可能会引发问题，但可被禁用。</span><span class="sxs-lookup"><span data-stu-id="403b5-173">This can be problematic, but can be disabled.</span></span> <span data-ttu-id="403b5-174">有关详细信息，请参阅 [ClickOnce 部署中的服务器和客户端配置问题](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)。</span><span class="sxs-lookup"><span data-stu-id="403b5-174">For more information, see [Server and Client Configuration Issues in ClickOnce Deployments](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).</span></span>  
  
 <span data-ttu-id="403b5-175">有关部署 XAML 浏览器应用程序 （XBAPs） 的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="403b5-175">For more information about deploying XAML browser applications (XBAPs), see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a><span data-ttu-id="403b5-176">安装 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="403b5-176">Installing the .NET Framework</span></span>  
 <span data-ttu-id="403b5-177">要运行 WPF 应用程序，必须在客户端上安装 Microsoft .NET 框架。</span><span class="sxs-lookup"><span data-stu-id="403b5-177">To run a WPF application, the Microsoft .NET Framework must be installed on the client.</span></span> <span data-ttu-id="403b5-178">当查看 WPF 浏览器托管的应用程序时，Internet Explorer 会自动检测客户端是否安装了 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="403b5-178">Internet Explorer automatically detects whether clients are installed with .NET Framework when WPF browser-hosted applications are viewed.</span></span> <span data-ttu-id="403b5-179">如果未安装 .NET 框架，Internet Explorer 会提示用户安装它。</span><span class="sxs-lookup"><span data-stu-id="403b5-179">If the .NET Framework is not installed, Internet Explorer prompts users to install it.</span></span>  
  
 <span data-ttu-id="403b5-180">为了检测是否安装了 .NET 框架，Internet Explorer 包括一个引导应用程序，该应用程序注册为具有以下扩展名的内容文件的回退多用途 Internet 邮件扩展 （MIME） 处理程序：.xaml、.xps、.xbap和 .应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-180">To detect whether the .NET Framework is installed, Internet Explorer includes a bootstrapper application that is registered as the fallback Multipurpose Internet Mail Extensions (MIME) handler for content files with the following extensions: .xaml, .xps, .xbap, and .application.</span></span> <span data-ttu-id="403b5-181">如果导航到这些文件类型，并且未在客户端上安装 .NET Framework，则引导程序应用程序将请求安装它的权限。</span><span class="sxs-lookup"><span data-stu-id="403b5-181">If you navigate to these file types and the .NET Framework is not installed on the client, the bootstrapper application requests permission to install it.</span></span> <span data-ttu-id="403b5-182">如果未提供权限，则既不安装 .NET 框架，也不会安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="403b5-182">If permission is not provided, neither the .NET Framework nor the application is installed.</span></span>  
  
 <span data-ttu-id="403b5-183">如果授予权限，Internet Explorer 将使用 Microsoft 后台智能传输服务 （BITS） 下载并安装 .NET 框架。</span><span class="sxs-lookup"><span data-stu-id="403b5-183">If permission is granted, Internet Explorer downloads and installs the .NET Framework using the Microsoft Background Intelligent Transfer Service (BITS).</span></span> <span data-ttu-id="403b5-184">成功安装 .NET 框架后，在新的浏览器窗口中打开最初请求的文件。</span><span class="sxs-lookup"><span data-stu-id="403b5-184">After successful installation of the .NET Framework, the originally requested file is opened in a new browser window.</span></span>  
  
 <span data-ttu-id="403b5-185">有关详细信息，请参阅[部署 .NET Framework 和应用程序](../../deployment/index.md)。</span><span class="sxs-lookup"><span data-stu-id="403b5-185">For more information, see [Deploying the .NET Framework and Applications](../../deployment/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="403b5-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="403b5-186">See also</span></span>

- [<span data-ttu-id="403b5-187">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="403b5-187">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
- [<span data-ttu-id="403b5-188">安全性</span><span class="sxs-lookup"><span data-stu-id="403b5-188">Security</span></span>](../security-wpf.md)
