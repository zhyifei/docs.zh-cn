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
# <a name="deploy-a-wpf-application"></a>部署 WPF 应用程序

构建 Windows 演示基础 （WPF） 应用程序后，需要部署它们。 Windows 和 .NET 框架包括多种部署技术。 用于部署 WPF 应用程序的部署技术取决于应用程序类型。 本主题简要概述了每种部署技术，以及如何结合每种 WPF 应用程序类型的部署要求使用。

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a>部署技术  
 Windows 和 .NET 框架包括多种部署技术，包括：  
  
- XCopy 部署。  
  
- Windows 安装程序部署。  
  
- ClickOnce 部署。  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a>XCopy 部署  
 XCopy 部署是指使用 XCopy 命令行程序将文件从一个位置复制到另一个位置。 XCopy 部署适用于下列情况：  
  
- 应用程序是自包含的。 无需更新客户端，即可运行。  
  
- 应用程序文件必须从一个位置移动到另一个位置，例如从生成位置（本地磁盘、UNC 文件共享等）移动到发布位置（网站、UNC 文件共享等）。  
  
- 应用程序无需进行 Shell 集成（“开始”菜单快捷方式、桌面图标等）。  
  
 XCopy 适用于简单的部署方案；如果需要更为复杂的部署功能，则会限制使用 XCopy。 具体而言就是，使用 XCopy 往往会导致创建、执行并维护能以可靠方式管理部署的脚本，并进而产生相应的开销。 此外，XCopy 不支持版本控制、卸载或回滚。  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a>Windows Installer  
 Windows 安装程序允许将应用程序打包为可独立执行文件，以便轻松分发到客户端并运行。 此外，Windows 安装程序与 Windows 一起安装，并启用与桌面、"开始"菜单和程序控制面板的集成。  
  
 Windows 安装程序简化了应用程序的安装和卸载，但它不提供从版本控制的角度来看确保已安装的应用程序保持最新功能。  
  
 有关 Windows 安装程序的详细信息，请参阅[Windows 安装程序部署](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a>ClickOnce 部署  
 ClickOnce 支持针对非 Web 应用程序部署 Web 样式的应用程序。 应用程序会发布到 Web 或文件服务器，也会从 Web 或文件服务器进行部署。 尽管 ClickOnce 不支持 Windows 安装程序安装的应用程序的全部客户端功能，但它确实支持包含以下内容的子集：  
  
- 与“开始”菜单及“程序”控制面板集成。  
  
- 版本控制、回滚和卸载。  
  
- 联机安装模式，该模式始终会从部署位置启动应用程序。  
  
- 当有新版本发布时自动更新。  
  
- 注册文件扩展名。  
  
 有关单击"一次"的详细信息，请参阅[单击"一次安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)"。  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a>部署 WPF 应用程序  
 WPF 应用程序的部署选项取决于应用程序的类型。 从部署的角度来看，WPF 有三种重要的应用程序类型：  
  
- 独立应用程序。  
  
- 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 应用程序。  
  
- XAML 浏览器应用程序 （XBAP）。  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a>部署独立应用程序  
 使用 ClickOnce 或 Windows 安装程序部署独立应用程序。 无论使用哪一项，独立应用程序都要在完全信任的状态下才能运行。 完全信任将自动授予使用 Windows 安装程序部署的独立应用程序。 使用 ClickOnce 部署的独立应用程序不会自动授予完全信任。 相反，ClickOnce 会显示用户在安装独立应用程序之前必须接受的安全警告对话框。 如果接受，独立应用程序就会安装并被授予完全信任状态。 如果不接受，则独立应用程序不会安装。  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a>部署仅标记 XAML 应用程序  
 仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记页面通常发布到 Web 服务器（如 HTML 页面），并且可以使用 Internet Explorer 查看。 仅标记 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页面会按照 Internet 区域权限集定义的限制，在部分信任的安全沙箱内运行。 这为基于 HTML 的 Web 应用程序提供了等效的安全沙盒。  
  
 有关 WPF 应用程序安全性的详细信息，请参阅[安全](../security-wpf.md)。  
  
 通过使用 XCopy[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]或 Windows 安装程序，只能将标记页面安装到本地文件系统。 可以使用 Internet 资源管理器或 Windows 资源管理器查看这些页面。  
  
 有关 XAML 的详细信息，请参阅 [XAML 概述 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)。  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a>部署 XAML 浏览器应用程序  
 XBAP 是需要部署以下三个文件的编译应用程序：  
  
- *应用程序名称*.exe：可执行的程序集应用程序文件。  
  
- *应用程序名称*.xbap：部署清单。  
  
- *应用程序名称*.exe.manifest：应用程序清单。  
  
> [!NOTE]
> 有关部署和应用程序清单的详细信息，请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md)。  
  
 这些文件是在生成 XBAP 时生成的。 有关详细信息，请参阅[如何：创建新的 WPF 浏览器应用程序项目](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))。 与仅[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]标记页面一样，XBAP 通常发布到 Web 服务器并使用 Internet 资源管理器进行查看。  
  
 可以使用任何部署技术将 XBAP 部署到客户端。 但是，建议单击一次，因为它提供以下功能：  
  
1. 当有新版本发布时自动更新。  
  
2. 完全信任运行的 XBAP 的提升权限。  
  
 默认情况下，ClickOnce 会使用.deploy 扩展名来发布应用程序文件。 这可能会引发问题，但可被禁用。 有关详细信息，请参阅 [ClickOnce 部署中的服务器和客户端配置问题](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)。  
  
 有关部署 XAML 浏览器应用程序 （XBAPs） 的详细信息，请参阅[WPF XAML 浏览器应用程序概述](wpf-xaml-browser-applications-overview.md)。  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a>安装 .NET Framework  
 要运行 WPF 应用程序，必须在客户端上安装 Microsoft .NET 框架。 当查看 WPF 浏览器托管的应用程序时，Internet Explorer 会自动检测客户端是否安装了 .NET Framework。 如果未安装 .NET 框架，Internet Explorer 会提示用户安装它。  
  
 为了检测是否安装了 .NET 框架，Internet Explorer 包括一个引导应用程序，该应用程序注册为具有以下扩展名的内容文件的回退多用途 Internet 邮件扩展 （MIME） 处理程序：.xaml、.xps、.xbap和 .应用程序。 如果导航到这些文件类型，并且未在客户端上安装 .NET Framework，则引导程序应用程序将请求安装它的权限。 如果未提供权限，则既不安装 .NET 框架，也不会安装应用程序。  
  
 如果授予权限，Internet Explorer 将使用 Microsoft 后台智能传输服务 （BITS） 下载并安装 .NET 框架。 成功安装 .NET 框架后，在新的浏览器窗口中打开最初请求的文件。  
  
 有关详细信息，请参阅[部署 .NET Framework 和应用程序](../../deployment/index.md)。  
  
## <a name="see-also"></a>另请参阅

- [生成 WPF 应用程序](building-a-wpf-application-wpf.md)
- [安全性](../security-wpf.md)
