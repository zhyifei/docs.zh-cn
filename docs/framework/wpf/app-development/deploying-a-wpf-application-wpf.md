---
title: 部署应用
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 9d4b7dd0464960441410d8ff2a196f0912354e5f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741944"
---
# <a name="deploy-a-wpf-application"></a><span data-ttu-id="2c59b-102">部署 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="2c59b-102">Deploy a WPF Application</span></span>

<span data-ttu-id="2c59b-103">生成 Windows Presentation Foundation （WPF）应用程序后，需要部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c59b-103">After Windows Presentation Foundation (WPF) applications are built, they need to be deployed.</span></span> <span data-ttu-id="2c59b-104">Windows 和 .NET Framework 包括几种部署技术。</span><span class="sxs-lookup"><span data-stu-id="2c59b-104">Windows and the .NET Framework include several deployment technologies.</span></span> <span data-ttu-id="2c59b-105">用于部署 WPF 应用程序的部署技术取决于应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="2c59b-105">The deployment technology that is used to deploy a WPF application depends on the application type.</span></span> <span data-ttu-id="2c59b-106">本主题简要概述了每种部署技术，以及如何将它们与每个 WPF 应用程序类型的部署要求结合使用。</span><span class="sxs-lookup"><span data-stu-id="2c59b-106">This topic provides a brief overview of each deployment technology, and how they are used in conjunction with the deployment requirements of each WPF application type.</span></span>

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a><span data-ttu-id="2c59b-107">배포 기술</span><span class="sxs-lookup"><span data-stu-id="2c59b-107">Deployment Technologies</span></span>  
 <span data-ttu-id="2c59b-108">Windows 和 .NET Framework 包括几种部署技术，其中包括：</span><span class="sxs-lookup"><span data-stu-id="2c59b-108">Windows and the .NET Framework include several deployment technologies, including:</span></span>  
  
- <span data-ttu-id="2c59b-109">XCopy 배포.</span><span class="sxs-lookup"><span data-stu-id="2c59b-109">XCopy deployment.</span></span>  
  
- <span data-ttu-id="2c59b-110">Windows Installer 部署。</span><span class="sxs-lookup"><span data-stu-id="2c59b-110">Windows Installer deployment.</span></span>  
  
- <span data-ttu-id="2c59b-111">ClickOnce 배포.</span><span class="sxs-lookup"><span data-stu-id="2c59b-111">ClickOnce deployment.</span></span>  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a><span data-ttu-id="2c59b-112">XCopy 배포</span><span class="sxs-lookup"><span data-stu-id="2c59b-112">XCopy Deployment</span></span>  
 <span data-ttu-id="2c59b-113">XCopy 배포는 XCopy 명령줄 프로그램을 사용하여 한 위치에서 다른 위치로 파일을 복사하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-113">XCopy deployment refers to the use of the XCopy command-line program to copy files from one location to another.</span></span> <span data-ttu-id="2c59b-114">XCopy 배포는 다음과 같은 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-114">XCopy deployment is suitable under the following circumstances:</span></span>  
  
- <span data-ttu-id="2c59b-115">애플리케이션이 독립적이며,</span><span class="sxs-lookup"><span data-stu-id="2c59b-115">The application is self-contained.</span></span> <span data-ttu-id="2c59b-116">실행하기 위해 클라이언트를 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-116">It does not need to update the client to run.</span></span>  
  
- <span data-ttu-id="2c59b-117">应用程序文件必须从一个位置移到另一个位置，如从生成位置（本地磁盘、UNC 文件共享等）移动到发布位置（网站、UNC 文件共享等）。</span><span class="sxs-lookup"><span data-stu-id="2c59b-117">Application files must be moved from one location to another, such as from a build location (local disk, UNC file share, and so on) to a publish location (Web site, UNC file share, and so on).</span></span>  
  
- <span data-ttu-id="2c59b-118">애플리케이션에 셸 통합(시작 메뉴 바로 가기, 데스크톱 아이콘 등)이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-118">The application does not require shell integration (Start menu shortcut, desktop icon, and so on).</span></span>  
  
 <span data-ttu-id="2c59b-119">XCopy는 간단한 배포 시나리오에 적합하지만 좀더 복잡한 배포 기능이 필요한 경우 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-119">Although XCopy is suitable for simple deployment scenarios, it is limited when more complex deployment capabilities are required.</span></span> <span data-ttu-id="2c59b-120">특히 XCopy를 사용하면 강력한 방식으로 배포를 관리하기 위한 스크립트를 작성, 실행 및 유지 관리하는 오버헤드가 자주 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-120">In particular, using XCopy often incurs the overhead for creating, executing, and maintaining scripts for managing deployment in a robust way.</span></span> <span data-ttu-id="2c59b-121">또한 XCopy는 버전 관리, 제거 또는 롤백을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-121">Furthermore, XCopy does not support versioning, uninstallation, or rollback.</span></span>  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a><span data-ttu-id="2c59b-122">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="2c59b-122">Windows Installer</span></span>  
 <span data-ttu-id="2c59b-123">Windows Installer 允许将应用程序打包为独立的可执行文件，这些可轻松分发到客户端并运行。</span><span class="sxs-lookup"><span data-stu-id="2c59b-123">Windows Installer allows applications to be packaged as self-contained executables that can be easily distributed to clients and run.</span></span> <span data-ttu-id="2c59b-124">此外，Windows Installer 随 Windows 一起安装，可与桌面、"开始" 菜单和 "程序" 控制面板集成。</span><span class="sxs-lookup"><span data-stu-id="2c59b-124">Furthermore, Windows Installer is installed with Windows and enables integration with the desktop, the Start menu, and the Programs control panel.</span></span>  
  
 <span data-ttu-id="2c59b-125">Windows Installer 简化了应用程序的安装和卸载，但它并不提供用于确保已安装的应用程序从版本控制的角度保持最新的功能。</span><span class="sxs-lookup"><span data-stu-id="2c59b-125">Windows Installer simplifies the installation and uninstallation of applications, but it does not provide facilities for ensuring that installed applications are kept up-to-date from a versioning standpoint.</span></span>  
  
 <span data-ttu-id="2c59b-126">有关 Windows Installer 的详细信息，请参阅[Windows Installer 部署](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。</span><span class="sxs-lookup"><span data-stu-id="2c59b-126">For more information about Windows Installer, see [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a><span data-ttu-id="2c59b-127">ClickOnce 배포</span><span class="sxs-lookup"><span data-stu-id="2c59b-127">ClickOnce Deployment</span></span>  
 <span data-ttu-id="2c59b-128">ClickOnce 为非 Web 应用程序启用 Web 样式应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="2c59b-128">ClickOnce enables Web-style application deployment for non-Web applications.</span></span> <span data-ttu-id="2c59b-129">애플리케이션이 웹 또는 파일 서버에서 게시되고 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-129">Applications are published to and deployed from Web or file servers.</span></span> <span data-ttu-id="2c59b-130">尽管 ClickOnce 不支持 Windows Installer 安装应用程序所支持的所有客户端功能，但它确实支持包含以下内容的子集：</span><span class="sxs-lookup"><span data-stu-id="2c59b-130">Although ClickOnce does not support the full range of client features that Windows Installer-installed applications do, it does support a subset that includes the following:</span></span>  
  
- <span data-ttu-id="2c59b-131">시작 메뉴 및 프로그램 제어판과의 통합.</span><span class="sxs-lookup"><span data-stu-id="2c59b-131">Integration with the Start menu and Programs control panel.</span></span>  
  
- <span data-ttu-id="2c59b-132">버전 관리, 롤백 및 제거.</span><span class="sxs-lookup"><span data-stu-id="2c59b-132">Versioning, rollback, and uninstallation.</span></span>  
  
- <span data-ttu-id="2c59b-133">항상 배포 위치에서 애플리케이션을 시작하는 온라인 설치 모드.</span><span class="sxs-lookup"><span data-stu-id="2c59b-133">Online install mode, which always launches an application from the deployment location.</span></span>  
  
- <span data-ttu-id="2c59b-134">새 버전이 릴리스되는 경우 자동 업데이트.</span><span class="sxs-lookup"><span data-stu-id="2c59b-134">Automatic updating when new versions are released.</span></span>  
  
- <span data-ttu-id="2c59b-135">파일 확장명 등록.</span><span class="sxs-lookup"><span data-stu-id="2c59b-135">Registration of file extensions.</span></span>  
  
 <span data-ttu-id="2c59b-136">有关 ClickOnce 的详细信息，请参阅[Clickonce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。</span><span class="sxs-lookup"><span data-stu-id="2c59b-136">For more information about ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a><span data-ttu-id="2c59b-137">WPF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="2c59b-137">Deploying WPF Applications</span></span>  
 <span data-ttu-id="2c59b-138">WPF 应用程序的部署选项取决于应用程序的类型。</span><span class="sxs-lookup"><span data-stu-id="2c59b-138">The deployment options for a WPF application depend on the type of application.</span></span> <span data-ttu-id="2c59b-139">从部署的角度来看，WPF 具有三种重要的应用程序类型：</span><span class="sxs-lookup"><span data-stu-id="2c59b-139">From a deployment perspective, WPF has three significant application types:</span></span>  
  
- <span data-ttu-id="2c59b-140">독립 실행형 애플리케이션.</span><span class="sxs-lookup"><span data-stu-id="2c59b-140">Standalone applications.</span></span>  
  
- <span data-ttu-id="2c59b-141">마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 애플리케이션.</span><span class="sxs-lookup"><span data-stu-id="2c59b-141">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications.</span></span>  
  
- <span data-ttu-id="2c59b-142">XAML 浏览器应用程序（Xbap）。</span><span class="sxs-lookup"><span data-stu-id="2c59b-142">XAML browser applications (XBAPs).</span></span>  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a><span data-ttu-id="2c59b-143">독립 실행형 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="2c59b-143">Deploying Standalone Applications</span></span>  
 <span data-ttu-id="2c59b-144">使用 ClickOnce 或 Windows Installer 部署独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c59b-144">Standalone applications are deployed using either ClickOnce or Windows Installer.</span></span> <span data-ttu-id="2c59b-145">두 방법 모두 독립 실행형 애플리케이션을 실행하려면 완전 신뢰가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-145">Either way, standalone applications require full trust to run.</span></span> <span data-ttu-id="2c59b-146">将自动向使用 Windows Installer 部署的独立应用程序授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="2c59b-146">Full trust is automatically granted to standalone applications that are deployed using Windows Installer.</span></span> <span data-ttu-id="2c59b-147">使用 ClickOnce 部署的独立应用程序不会自动被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="2c59b-147">Standalone applications that are deployed using ClickOnce are not automatically granted full trust.</span></span> <span data-ttu-id="2c59b-148">相反，ClickOnce 会显示一个安全警告对话框，用户必须先接受该对话框，然后才能安装独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c59b-148">Instead, ClickOnce displays a security warning dialog that users must accept before a standalone application is installed.</span></span> <span data-ttu-id="2c59b-149">동의하면 독립 실행형 애플리케이션이 설치되고 완전 신뢰가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-149">If accepted, the standalone application is installed and granted full trust.</span></span> <span data-ttu-id="2c59b-150">동의하지 않으면 독립 실행형 애플리케이션이 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-150">If not, the standalone application is not installed.</span></span>  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a><span data-ttu-id="2c59b-151">마크업 전용 XAML 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="2c59b-151">Deploying Markup-Only XAML Applications</span></span>  
 <span data-ttu-id="2c59b-152">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面通常会发布到 Web 服务器（如 HTML 页面），可以使用 Internet Explorer 进行查看。</span><span class="sxs-lookup"><span data-stu-id="2c59b-152">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are usually published to Web servers, like HTML pages, and can be viewed using Internet Explorer.</span></span> <span data-ttu-id="2c59b-153">마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 인터넷 영역 권한 설정에 정의된 제한 사항이 있는 부분 신뢰 보안 샌드박스 내에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-153">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages run within a partial-trust security sandbox with restrictions that are defined by the Internet zone permission set.</span></span> <span data-ttu-id="2c59b-154">这为基于 HTML 的 Web 应用程序提供了等效的安全沙箱。</span><span class="sxs-lookup"><span data-stu-id="2c59b-154">This provides an equivalent security sandbox to HTML-based Web applications.</span></span>  
  
 <span data-ttu-id="2c59b-155">有关 WPF 应用程序安全性的详细信息，请参阅[安全性](../security-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="2c59b-155">For more information about security for WPF applications, see [Security](../security-wpf.md).</span></span>  
  
 <span data-ttu-id="2c59b-156">仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面可以使用 XCopy 或 Windows Installer 安装到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="2c59b-156">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages can be installed to the local file system by using either XCopy or Windows Installer.</span></span> <span data-ttu-id="2c59b-157">可以使用 Internet Explorer 或 Windows 资源管理器查看这些页面。</span><span class="sxs-lookup"><span data-stu-id="2c59b-157">These pages can be viewed using Internet Explorer or Windows Explorer.</span></span>  
  
 <span data-ttu-id="2c59b-158">XAML에 대한 자세한 내용은 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c59b-158">For more information about XAML, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a><span data-ttu-id="2c59b-159">XAML 브라우저 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="2c59b-159">Deploying XAML Browser Applications</span></span>  
 <span data-ttu-id="2c59b-160">Xbap 是已编译的应用程序，需要部署以下三个文件：</span><span class="sxs-lookup"><span data-stu-id="2c59b-160">XBAPs are compiled applications that require the following three files to be deployed:</span></span>  
  
- <span data-ttu-id="2c59b-161">*ApplicationName*.exe: 실행 가능한 어셈블리 애플리케이션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-161">*ApplicationName*.exe: The executable assembly application file.</span></span>  
  
- <span data-ttu-id="2c59b-162">*ApplicationName*.xbap: 배포 매니페스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-162">*ApplicationName*.xbap: The deployment manifest.</span></span>  
  
- <span data-ttu-id="2c59b-163">*ApplicationName*.exe.manifest: 애플리케이션 매니페스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-163">*ApplicationName*.exe.manifest: The application manifest.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c59b-164">배포 및 애플리케이션 매니페스트에 대한 자세한 내용은 [WPF 애플리케이션 만들기](building-a-wpf-application-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c59b-164">For more information about deployment and application manifests, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="2c59b-165">这些文件是在生成 XBAP 时生成的。</span><span class="sxs-lookup"><span data-stu-id="2c59b-165">These files are produced when an XBAP is built.</span></span> <span data-ttu-id="2c59b-166">자세한 내용은 [방법: 새 WPF 브라우저 애플리케이션 프로젝트 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c59b-166">For more information, see [How to: Create a New WPF Browser Application Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).</span></span> <span data-ttu-id="2c59b-167">与仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面一样，Xbap 通常会发布到 Web 服务器，并使用 Internet Explorer 进行查看。</span><span class="sxs-lookup"><span data-stu-id="2c59b-167">Like markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages, XBAPs are typically published to a Web server and viewed using Internet Explorer.</span></span>  
  
 <span data-ttu-id="2c59b-168">可以使用任何一种部署技术将 Xbap 部署到客户端。</span><span class="sxs-lookup"><span data-stu-id="2c59b-168">XBAPs can be deployed to clients using any of the deployment techniques.</span></span> <span data-ttu-id="2c59b-169">但建议使用 ClickOnce，因为它提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="2c59b-169">However, ClickOnce is recommended since it provides the following capabilities:</span></span>  
  
1. <span data-ttu-id="2c59b-170">새 버전이 게시될 때 자동 업데이트.</span><span class="sxs-lookup"><span data-stu-id="2c59b-170">Automatic updates when a new version is published.</span></span>  
  
2. <span data-ttu-id="2c59b-171">以完全信任级别运行的 XBAP 的提升权限。</span><span class="sxs-lookup"><span data-stu-id="2c59b-171">Elevation privileges for the XBAP running with full trust.</span></span>  
  
 <span data-ttu-id="2c59b-172">기본적으로 ClickOnce는 .deploy 확장명을 사용하여 애플리케이션 파일을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-172">By default, ClickOnce publishes application files with the .deploy extension.</span></span> <span data-ttu-id="2c59b-173">그러면 문제가 될 수 있지만 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c59b-173">This can be problematic, but can be disabled.</span></span> <span data-ttu-id="2c59b-174">자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c59b-174">For more information, see [Server and Client Configuration Issues in ClickOnce Deployments](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).</span></span>  
  
 <span data-ttu-id="2c59b-175">有关部署 XAML 浏览器应用程序（Xbap）的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2c59b-175">For more information about deploying XAML browser applications (XBAPs), see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a><span data-ttu-id="2c59b-176">.NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="2c59b-176">Installing the .NET Framework</span></span>  
 <span data-ttu-id="2c59b-177">若要运行 WPF 应用程序，Microsoft .NET 框架必须安装在客户端上。</span><span class="sxs-lookup"><span data-stu-id="2c59b-177">To run a WPF application, the Microsoft .NET Framework must be installed on the client.</span></span> <span data-ttu-id="2c59b-178">当查看 WPF 浏览器承载的应用程序时，Internet Explorer 会自动检测是否随 .NET Framework 一起安装了客户端。</span><span class="sxs-lookup"><span data-stu-id="2c59b-178">Internet Explorer automatically detects whether clients are installed with .NET Framework when WPF browser-hosted applications are viewed.</span></span> <span data-ttu-id="2c59b-179">如果未安装 .NET Framework，Internet Explorer 将提示用户安装。</span><span class="sxs-lookup"><span data-stu-id="2c59b-179">If the .NET Framework is not installed, Internet Explorer prompts users to install it.</span></span>  
  
 <span data-ttu-id="2c59b-180">为了检测 .NET Framework 是否已安装，Internet Explorer 包括一个引导程序应用程序，该应用程序已注册为具有以下扩展名的内容文件的后备多用途 Internet 邮件扩展（MIME）处理程序： .xaml、.xps、xbap、和。</span><span class="sxs-lookup"><span data-stu-id="2c59b-180">To detect whether the .NET Framework is installed, Internet Explorer includes a bootstrapper application that is registered as the fallback Multipurpose Internet Mail Extensions (MIME) handler for content files with the following extensions: .xaml, .xps, .xbap, and .application.</span></span> <span data-ttu-id="2c59b-181">如果你导航到这些文件类型，并且客户端上未安装 .NET Framework，则引导程序应用程序会请求安装它的权限。</span><span class="sxs-lookup"><span data-stu-id="2c59b-181">If you navigate to these file types and the .NET Framework is not installed on the client, the bootstrapper application requests permission to install it.</span></span> <span data-ttu-id="2c59b-182">如果未提供权限，则不会安装 .NET Framework 和应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c59b-182">If permission is not provided, neither the .NET Framework nor the application is installed.</span></span>  
  
 <span data-ttu-id="2c59b-183">如果授予了权限，Internet Explorer 将使用 Microsoft 后台智能传输服务（BITS）下载并安装 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="2c59b-183">If permission is granted, Internet Explorer downloads and installs the .NET Framework using the Microsoft Background Intelligent Transfer Service (BITS).</span></span> <span data-ttu-id="2c59b-184">成功安装 .NET Framework 后，最初请求的文件将在新的浏览器窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="2c59b-184">After successful installation of the .NET Framework, the originally requested file is opened in a new browser window.</span></span>  
  
 <span data-ttu-id="2c59b-185">자세한 내용은 [.NET Framework 및 애플리케이션 배포](../../deployment/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c59b-185">For more information, see [Deploying the .NET Framework and Applications](../../deployment/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c59b-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c59b-186">See also</span></span>

- [<span data-ttu-id="2c59b-187">WPF 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="2c59b-187">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
- [<span data-ttu-id="2c59b-188">Security</span><span class="sxs-lookup"><span data-stu-id="2c59b-188">Security</span></span>](../security-wpf.md)
