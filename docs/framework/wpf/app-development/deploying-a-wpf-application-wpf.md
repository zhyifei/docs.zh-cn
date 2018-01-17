---
title: "部署 WPF 应用程序 (WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c7addef624ee8a41e2f421e0d912efbbaac6eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-a-wpf-application-wpf"></a>部署 WPF 应用程序 (WPF)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 应用程序在生成后需要进行部署。 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 和 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 包含多项部署技术。 用于部署 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序的部署技术取决于应用程序的类型。 本主题将简要概述各项部署技术，以及如何使用这些技术来满足各类 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序的部署要求。  
  
   
<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>部署技术  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 和 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 包含多项部署技术，其中包括：  
  
-   XCopy 部署。  
  
-   [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 部署。  
  
-   [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 部署。  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>XCopy 部署  
 XCopy 部署是指使用 XCopy 命令行程序将文件从一个位置复制到另一个位置。 XCopy 部署适用于下列情况：  
  
-   应用程序是自包含的。 无需更新客户端，即可运行。  
  
-   应用程序文件必须从一个位置移到另一个位置，如从生成位置（本地磁盘、[!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] 文件共享等）移到发布位置（网站、[!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] 文件共享等）。  
  
-   应用程序无需进行 Shell 集成（“开始”菜单快捷方式、桌面图标等）。  
  
 XCopy 适用于简单的部署方案；如果需要更为复杂的部署功能，则会限制使用 XCopy。 具体而言就是，使用 XCopy 往往会导致创建、执行并维护能以可靠方式管理部署的脚本，并进而产生相应的开销。 此外，XCopy 不支持版本控制、卸载或回滚。  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 允许应用程序打包为可轻松分发到客户端并运行的自包含可执行文件。 此外，[!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 会随 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 一起安装，并能与桌面、“开始”菜单及“程序”控制面板集成。  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 简化了应用程序的安装和卸载，但它不会提供相应工具以确保已安装的应用程序始终为最新版本。  
  
 有关 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 的详细信息，请参阅 [Windows Installer 部署](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)。  
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>ClickOnce 部署  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 能够针对非 Web 应用程序进行 Web 样式应用程序部署。 应用程序会发布到 Web 或文件服务器，也会从 Web 或文件服务器进行部署。 尽管 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 不支持 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 安装的应用程序所支持的所有客户端功能，但它支持其中的部分功能，包括：  
  
-   与“开始”菜单及“程序”控制面板集成。  
  
-   版本控制、回滚和卸载。  
  
-   联机安装模式，该模式始终会从部署位置启动应用程序。  
  
-   当有新版本发布时自动更新。  
  
-   注册文件扩展名。  
  
 有关 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 的详细信息，请参阅 [ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>部署 WPF 应用程序  
 适用于 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序的部署选项取决于应用程序的类型。 从部署的角度来看，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 共有三种重要的应用程序类型：  
  
-   独立应用程序。  
  
-   仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 应用程序。  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]。  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>部署独立应用程序  
 独立应用程序使用 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 或 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 来部署。 无论使用哪一项，独立应用程序都要在完全信任的状态下才能运行。 使用 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 部署的独立应用程序会被自动授予完全信任状态。 使用 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 部署的独立应用程序不会被自动授予完全信任状态。 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 会转而显示安全警告对话框，用户必须先执行接受操作，然后独立应用程序才会安装。 如果接受，独立应用程序就会安装并被授予完全信任状态。 如果不接受，则独立应用程序不会安装。  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>部署仅标记 XAML 应用程序  
 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面通常会发布到 Web 服务器（如 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 页面），并可以使用 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 来查看。 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面会按照 Internet 区域权限集定义的限制，在部分信任的安全沙箱内运行。 这样即可提供一个与基于 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 的 Web 应用程序一样安全的沙箱。  
  
 有关 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序安全性的详细信息，请参阅[安全性](../../../../docs/framework/wpf/security-wpf.md)。  
  
 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面可以利用 XCopy 或 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] 安装到本地文件系统。 这些页面可以使用 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 或 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 资源管理器来查看。  
  
 有关 XAML 的详细信息，请参阅 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)。  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>部署 XAML 浏览器应用程序  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 是需要部署以下三个文件的编译型应用程序：  
  
-   *应用程序名称*.exe：可执行的程序集应用程序文件。  
  
-   *应用程序名称*.xbap：部署清单。  
  
-   *应用程序名称*.exe.manifest：应用程序清单。  
  
> [!NOTE]
>  有关部署和应用程序清单的详细信息，请参阅[生成 WPF 应用程序](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)。  
  
 这些文件在 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 生成时产生。 有关详细信息，请参阅[如何：创建新的 WPF 浏览器应用程序项目](http://msdn.microsoft.com/en-us/72ef4d90-e163-42a1-8df0-ea7ccfd1901f)。 和仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面一样，[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 通常会发布到 Web 服务器并使用 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 来查看。  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可以使用任意部署技术部署到客户端。 但是，建议使用 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]，因为它提供以下功能：  
  
1.  当有新版本发布时自动更新。  
  
2.  适用于在完全信任状态下运行的 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 的提升权限。  
  
 默认情况下，ClickOnce 会使用.deploy 扩展名来发布应用程序文件。 这可能会引发问题，但可被禁用。 有关详细信息，请参阅 [ClickOnce 部署中的服务器和客户端配置问题](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)。  
  
 有关部署 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 的详细信息，请参阅 [WPF XAML 浏览器应用程序概述](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)。  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>安装 .NET Framework  
 要运行 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序，必须先在客户端上安装 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]。 当查看 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 浏览器承载的应用程序时，[!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 会自动检测客户端是否已安装 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]。 如果 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 尚未安装，则 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 会提示用户安装。  
  
 为检测 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 是否已安装，[!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 含有一个引导应用程序，该应用程序会被注册为具有以下扩展名的内容文件的回退 [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 处理程序：.xaml、.xps、.xbap 和 .application。 如果导航到这些文件类型，且客户端上还未安装 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]，则该引导应用程序会请求相应权限以完成安装。 如果未被授予相应权限，则 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 和应用程序都不会安装。  
  
 如果被授予了相应权限，则 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 会使用 [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)] 下载并安装 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]。 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 成功安装好后，最初请求的文件会在新的浏览器窗口中打开。  
  
 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] 自动检测适用于装有 [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] 或更高版本的 [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)]、[!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)] 和 [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] 客户端。  
  
 有关详细信息，请参阅[部署 .NET Framework 和应用程序](../../../../docs/framework/deployment/index.md)。  
  
## <a name="see-also"></a>请参阅  
 [生成 WPF 应用程序](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [安全性](../../../../docs/framework/wpf/security-wpf.md)
