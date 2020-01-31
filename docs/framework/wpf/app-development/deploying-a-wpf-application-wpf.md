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
# <a name="deploy-a-wpf-application"></a>部署 WPF 应用程序

生成 Windows Presentation Foundation （WPF）应用程序后，需要部署这些应用程序。 Windows 和 .NET Framework 包括几种部署技术。 用于部署 WPF 应用程序的部署技术取决于应用程序类型。 本主题简要概述了每种部署技术，以及如何将它们与每个 WPF 应用程序类型的部署要求结合使用。

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>배포 기술  
 Windows 和 .NET Framework 包括几种部署技术，其中包括：  
  
- XCopy 배포.  
  
- Windows Installer 部署。  
  
- ClickOnce 배포.  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>XCopy 배포  
 XCopy 배포는 XCopy 명령줄 프로그램을 사용하여 한 위치에서 다른 위치로 파일을 복사하는 방법을 나타냅니다. XCopy 배포는 다음과 같은 경우에 적합합니다.  
  
- 애플리케이션이 독립적이며, 실행하기 위해 클라이언트를 업데이트할 필요가 없습니다.  
  
- 应用程序文件必须从一个位置移到另一个位置，如从生成位置（本地磁盘、UNC 文件共享等）移动到发布位置（网站、UNC 文件共享等）。  
  
- 애플리케이션에 셸 통합(시작 메뉴 바로 가기, 데스크톱 아이콘 등)이 필요하지 않습니다.  
  
 XCopy는 간단한 배포 시나리오에 적합하지만 좀더 복잡한 배포 기능이 필요한 경우 제한됩니다. 특히 XCopy를 사용하면 강력한 방식으로 배포를 관리하기 위한 스크립트를 작성, 실행 및 유지 관리하는 오버헤드가 자주 발생합니다. 또한 XCopy는 버전 관리, 제거 또는 롤백을 지원하지 않습니다.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 Windows Installer 允许将应用程序打包为独立的可执行文件，这些可轻松分发到客户端并运行。 此外，Windows Installer 随 Windows 一起安装，可与桌面、"开始" 菜单和 "程序" 控制面板集成。  
  
 Windows Installer 简化了应用程序的安装和卸载，但它并不提供用于确保已安装的应用程序从版本控制的角度保持最新的功能。  
  
 有关 Windows Installer 的详细信息，请参阅[Windows Installer 部署](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>ClickOnce 배포  
 ClickOnce 为非 Web 应用程序启用 Web 样式应用程序部署。 애플리케이션이 웹 또는 파일 서버에서 게시되고 배포됩니다. 尽管 ClickOnce 不支持 Windows Installer 安装应用程序所支持的所有客户端功能，但它确实支持包含以下内容的子集：  
  
- 시작 메뉴 및 프로그램 제어판과의 통합.  
  
- 버전 관리, 롤백 및 제거.  
  
- 항상 배포 위치에서 애플리케이션을 시작하는 온라인 설치 모드.  
  
- 새 버전이 릴리스되는 경우 자동 업데이트.  
  
- 파일 확장명 등록.  
  
 有关 ClickOnce 的详细信息，请参阅[Clickonce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>WPF 애플리케이션 배포  
 WPF 应用程序的部署选项取决于应用程序的类型。 从部署的角度来看，WPF 具有三种重要的应用程序类型：  
  
- 독립 실행형 애플리케이션.  
  
- 마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 애플리케이션.  
  
- XAML 浏览器应用程序（Xbap）。  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>독립 실행형 애플리케이션 배포  
 使用 ClickOnce 或 Windows Installer 部署独立的应用程序。 두 방법 모두 독립 실행형 애플리케이션을 실행하려면 완전 신뢰가 필요합니다. 将自动向使用 Windows Installer 部署的独立应用程序授予完全信任。 使用 ClickOnce 部署的独立应用程序不会自动被授予完全信任。 相反，ClickOnce 会显示一个安全警告对话框，用户必须先接受该对话框，然后才能安装独立的应用程序。 동의하면 독립 실행형 애플리케이션이 설치되고 완전 신뢰가 부여됩니다. 동의하지 않으면 독립 실행형 애플리케이션이 설치되지 않습니다.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>마크업 전용 XAML 애플리케이션 배포  
 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面通常会发布到 Web 服务器（如 HTML 页面），可以使用 Internet Explorer 进行查看。 마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 인터넷 영역 권한 설정에 정의된 제한 사항이 있는 부분 신뢰 보안 샌드박스 내에서 실행됩니다. 这为基于 HTML 的 Web 应用程序提供了等效的安全沙箱。  
  
 有关 WPF 应用程序安全性的详细信息，请参阅[安全性](../security-wpf.md)。  
  
 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面可以使用 XCopy 或 Windows Installer 安装到本地文件系统。 可以使用 Internet Explorer 或 Windows 资源管理器查看这些页面。  
  
 XAML에 대한 자세한 내용은 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)를 참조하세요.  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>XAML 브라우저 애플리케이션 배포  
 Xbap 是已编译的应用程序，需要部署以下三个文件：  
  
- *ApplicationName*.exe: 실행 가능한 어셈블리 애플리케이션 파일입니다.  
  
- *ApplicationName*.xbap: 배포 매니페스트입니다.  
  
- *ApplicationName*.exe.manifest: 애플리케이션 매니페스트입니다.  
  
> [!NOTE]
> 배포 및 애플리케이션 매니페스트에 대한 자세한 내용은 [WPF 애플리케이션 만들기](building-a-wpf-application-wpf.md)를 참조하세요.  
  
 这些文件是在生成 XBAP 时生成的。 자세한 내용은 [방법: 새 WPF 브라우저 애플리케이션 프로젝트 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))를 참조하세요. 与仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面一样，Xbap 通常会发布到 Web 服务器，并使用 Internet Explorer 进行查看。  
  
 可以使用任何一种部署技术将 Xbap 部署到客户端。 但建议使用 ClickOnce，因为它提供以下功能：  
  
1. 새 버전이 게시될 때 자동 업데이트.  
  
2. 以完全信任级别运行的 XBAP 的提升权限。  
  
 기본적으로 ClickOnce는 .deploy 확장명을 사용하여 애플리케이션 파일을 게시합니다. 그러면 문제가 될 수 있지만 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)를 참조하세요.  
  
 有关部署 XAML 浏览器应用程序（Xbap）的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>.NET Framework 설치  
 若要运行 WPF 应用程序，Microsoft .NET 框架必须安装在客户端上。 当查看 WPF 浏览器承载的应用程序时，Internet Explorer 会自动检测是否随 .NET Framework 一起安装了客户端。 如果未安装 .NET Framework，Internet Explorer 将提示用户安装。  
  
 为了检测 .NET Framework 是否已安装，Internet Explorer 包括一个引导程序应用程序，该应用程序已注册为具有以下扩展名的内容文件的后备多用途 Internet 邮件扩展（MIME）处理程序： .xaml、.xps、xbap、和。 如果你导航到这些文件类型，并且客户端上未安装 .NET Framework，则引导程序应用程序会请求安装它的权限。 如果未提供权限，则不会安装 .NET Framework 和应用程序。  
  
 如果授予了权限，Internet Explorer 将使用 Microsoft 后台智能传输服务（BITS）下载并安装 .NET Framework。 成功安装 .NET Framework 后，最初请求的文件将在新的浏览器窗口中打开。  
  
 자세한 내용은 [.NET Framework 및 애플리케이션 배포](../../deployment/index.md)를 참조하세요.  
  
## <a name="see-also"></a>另请参阅

- [WPF 애플리케이션 빌드](building-a-wpf-application-wpf.md)
- [Security](../security-wpf.md)
