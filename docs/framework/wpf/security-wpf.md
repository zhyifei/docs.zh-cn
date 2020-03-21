---
title: 安全性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: e0a56dcbf8d151fcb0d4f6271ecba15c0ff955a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174610"
---
# <a name="security-wpf"></a>安全性 (WPF)
<a name="introduction"></a>在开发 Windows 演示文稿基础 （WPF） 独立和浏览器托管的应用程序时，必须考虑安全模型。 WPF 独立应用程序以不受限制的权限（CAS**完全信任**权限集）执行，无论是使用 Windows 安装程序 （.msi）、XCopy 还是 ClickOnce 部署。 不支持使用 ClickOnce 部署部分信任的独立 WPF 应用程序。 但是，完全信任的主机应用程序可以使用 .NET 框架外<xref:System.AppDomain>接程序模型创建部分信任。 有关详细信息，请参阅[WPF 加载项概述](./app-development/wpf-add-ins-overview.md)。  
  
 WPF浏览器托管的应用程序由 Windows Internet 资源管理器或 Firefox 托管，可以是 XAML 浏览器应用程序 （XBAPs） 或松散[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]文档 有关详细信息，请参阅[WPF XAML 浏览器应用程序概述](./app-development/wpf-xaml-browser-applications-overview.md)。  
  
 默认情况下，WPF 浏览器托管的应用程序在部分信任安全沙盒中执行，该沙盒仅限于默认的 CAS**Internet**区域权限集。 这将有效地将 WPF 浏览器托管的应用程序与客户端计算机隔离，就像您希望将典型的 Web 应用程序隔离一样。 XBAP 最高可以将权限提升到“完全信任”，具体取决于部署 URL 的安全区域和客户端的安全配置。 有关详细信息，请参阅[WPF 部分信任安全](wpf-partial-trust-security.md)。  
  
 本主题讨论 Windows 演示文稿基础 （WPF） 独立和浏览器托管应用程序的安全模型。  
  
 本主题包含以下各节：  
  
- [安全导航](#SafeTopLevelNavigation)  
  
- [Web 浏览软件安全设置](#InternetExplorerSecuritySettings)  
  
- [WebBrowser 控件和功能控件](#webbrowser_control_and_feature_controls)  
  
- [对部分受信任的客户端应用程序禁用 APTCA 程序集](#APTCA)  
  
- [宽松 XAML 文件的沙盒行为](#LooseContentSandboxing)  
  
- [用于开发可提高安全性的 WPF 应用程序的资源](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>
## <a name="safe-navigation"></a>安全导航  
 对于 XBAP，WPF 区分两种类型的导航：应用程序和浏览器。  
  
 应用程序导航** 是指在浏览器托管的应用程序内的内容项之间进行导航。 浏览器导航** 是指可更改浏览器自身的内容和位置 URL 的导航。 应用程序导航（通常为 XAML）和浏览器导航（通常 HTML）之间的关系如下图所示：
  
 ![应用程序导航和浏览器导航之间的关系。](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 XBAP 导航到的内容类型主要取决于是否使用应用程序导航或浏览器导航。  
  
<a name="Application_Navigation_Security"></a>
### <a name="application-navigation-security"></a>应用程序导航安全性  
 如果可以使用包 URI 进行标识，则应用程序导航被视为安全，该 URI 支持四种类型的内容：  
  
|内容类型|说明|URI 示例|  
|------------------|-----------------|-----------------|  
|资源|添加到具有生成类型的**资源**的项目的文件。|`pack://application:,,,/MyResourceFile.xaml`|  
|内容|添加到具有生成**类型内容**的项目的文件。|`pack://application:,,,/MyContentFile.xaml`|  
|源站点|添加到生成类型的 **"无"** 的项目的文件。|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|应用程序代码|具有已编译代码隐藏的 XAML 资源。<br /><br /> -或-<br /><br /> 添加到具有生成类型的**Page**的项目的 XAML 文件。|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> 有关应用程序数据文件和打包 URI 的详细信息，请参阅[WPF 应用程序资源、内容和数据文件](./app-development/wpf-application-resource-content-and-data-files.md)。  
  
 可以由用户导航到这些内容类型的文件，也可以通过编程方式导航到这些内容类型的文件：  
  
- **用户导航**。 用户通过单击<xref:System.Windows.Documents.Hyperlink>元素进行导航。  
  
- **编程导航**。 应用程序导航时不涉及用户，例如，通过设置<xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>属性。  
  
<a name="Browser_Navigation_Security"></a>
### <a name="browser-navigation-security"></a>浏览器导航安全性  
 浏览器导航仅在以下条件下被视为安全：  
  
- **用户导航**。 用户通过单击<xref:System.Windows.Documents.Hyperlink>主<xref:System.Windows.Navigation.NavigationWindow>元素中的元素而不是嵌套<xref:System.Windows.Controls.Frame>中进行导航。  
  
- **区域**。 要导航到的内容位于 Internet 或本地 Intranet 上。  
  
- **协议**。 **file**正在使用的协议是**http****http、https、** 文件或**mailto**。  
  
 如果 XBAP 尝试以不符合这些条件的方式导航到内容，则引发 。 <xref:System.Security.SecurityException>  
  
<a name="InternetExplorerSecuritySettings"></a>
## <a name="web-browsing-software-security-settings"></a>Web 浏览软件安全设置  
 计算机上的安全设置决定了任何 Web 浏览软件被授予的访问权限。 Web 浏览软件包括使用[WinINet](/windows/win32/wininet/portal)或[UrlMon](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) API 的任何应用程序或组件，包括 Internet 资源管理器和演示Host.exe。  
  
 Internet Explorer 提供了一种机制，通过该机制可以配置允许由 Internet Explorer 执行的功能，包括以下内容：  
  
- .NET 框架依赖组件  
  
- ActiveX 控件和插件  
  
- 下载  
  
- 脚本编写  
  
- 用户身份验证  
  
 以这种方式保护的功能集合按区域配置，用于**Internet、Intranet、****受信任的站点**和**受限站点**区域。 **Internet** 以下步骤描述如何配置安全设置：  
  
1. 打开“控制面板”****。  
  
2. 点击**网络和互联网**，然后单击**互联网选项**。  
  
     将显示“Internet 选项”对话框。  
  
3. 在 **"安全"** 选项卡上，选择要为其配置安全设置的区域。  
  
4. 单击 **"自定义级别"** 按钮。  
  
     将显示 **"安全设置"** 对话框，您可以配置所选区域的安全设置。  
  
     ![显示"安全设置"对话框的屏幕截图。](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> 也可以从 Internet Explorer 中进入“Internet 选项”对话框。 单击**工具**，然后单击**互联网选项**。  
  
 从 Windows Internet 资源管理器 7 开始，包括针对 .NET 框架的以下安全设置：  
  
- **宽松 XAML**。 控制 Internet 资源管理器是否可以导航到和[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]松散的文件。 （“启用”、“禁用”和“提示”选项）。  
  
- **XAML 浏览器应用程序**。 控制 Internet 资源管理器是否可以导航到并运行 XBAP。 （“启用”、“禁用”和“提示”选项）。  
  
 默认情况下，这些设置都为**Internet、****本地 Intranet**和**受信任的站点**区域启用，并且为**受限站点**区域禁用。  
  
<a name="Security_Settings_for_IE6_and_Below"></a>
### <a name="security-related-wpf-registry-settings"></a>与安全相关的 WPF 注册表设置  
 除了可通过“Internet 选项”设置的安全设置之外，还可以通过设置以下注册表值有选择地阻止许多安全敏感 WPF 功能。 这些值在以下注册表项下定义：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 下表列出了可以设置的值。  
  
|值名称|值类型|值数据|  
|----------------|----------------|----------------|  
|XBAPDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|LooseXamlDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|WebBrowserDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|MediaAudioDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|MediaImageDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|MediaVideoDisallow|REG_DWORD|1 为禁止；0 为允许。|  
|ScriptInteropDisallow|REG_DWORD|1 为禁止；0 为允许。|  
  
<a name="webbrowser_control_and_feature_controls"></a>
## <a name="webbrowser-control-and-feature-controls"></a>WebBrowser 控件和功能控件  
 WPF<xref:System.Windows.Controls.WebBrowser>控件可用于托管 Web 内容。 WPF<xref:System.Windows.Controls.WebBrowser>控件包装基础 Web 浏览器 ActiveX 控件。 当您使用 WPF<xref:System.Windows.Controls.WebBrowser>控件托管不受信任的 Web 内容时，WPF 为保护应用程序提供了一些支持。 但是，某些安全功能必须由使用控件<xref:System.Windows.Controls.WebBrowser>的应用程序直接应用。 有关 Web 浏览器 ActiveX 控件的详细信息，请参阅[Web 浏览器控件概述和教程](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85))。  
  
> [!NOTE]
> 本节也适用于控件，<xref:System.Windows.Controls.Frame>因为它使用<xref:System.Windows.Controls.WebBrowser>导航到 HTML 内容。  
  
 如果 WPF<xref:System.Windows.Controls.WebBrowser>控件用于托管不受信任的 Web 内容，则应用程序应使用部分信任<xref:System.AppDomain>来帮助将应用程序代码与潜在的恶意 HTML 脚本代码隔离。 如果应用程序使用<xref:System.Windows.Controls.WebBrowser.InvokeScript%2A>方法和<xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>属性与托管脚本交互，则尤其如此。 有关详细信息，请参阅[WPF 加载项概述](./app-development/wpf-add-ins-overview.md)。  
  
 如果应用程序使用 WPF<xref:System.Windows.Controls.WebBrowser>控件，则提高安全性和缓解攻击的另一种方法是启用 Internet Explorer 功能控件。 功能控件是 Internet 资源管理器的补充，允许管理员和开发人员配置 Internet Explorer 的功能以及承载 WebBrowser ActiveX 控件的应用程序，WPF<xref:System.Windows.Controls.WebBrowser>控件将该控件包装。 可以使用[CoInternetSetFeature 启用功能](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85))或更改注册表中的值来配置功能控件。 有关功能控件的详细信息，请参阅[功能控制和](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) [Internet 功能控件](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85))简介。  
  
 如果您正在开发使用 WPF 控件的独立 WPF<xref:System.Windows.Controls.WebBrowser>应用程序，WPF 会自动为应用程序启用以下功能控件。  
  
|功能控件|  
|---------------------|  
|FEATURE_MIME_HANDLING|  
|FEATURE_MIME_SNIFFING|  
|FEATURE_OBJECT_CACHING|  
|FEATURE_SAFE_BINDTOOBJECT|  
|FEATURE_WINDOW_RESTRICTIONS|  
|FEATURE_ZONE_ELEVATION|  
|FEATURE_RESTRICT_FILEDOWNLOAD|  
|FEATURE_RESTRICT_ACTIVEXINSTALL|  
|FEATURE_ADDON_MANAGEMENT|  
|FEATURE_HTTP_USERNAME_PASSWORD_DISABLE|  
|FEATURE_SECURITYBAND|  
|FEATURE_UNC_SAVEDFILECHECK|  
|FEATURE_VALIDATE_NAVIGATE_URL|  
|FEATURE_DISABLE_TELNET_PROTOCOL|  
|FEATURE_WEBOC_POPUPMANAGEMENT|  
|FEATURE_DISABLE_LEGACY_COMPRESSION|  
|FEATURE_SSLUX|  
  
 由于这些功能控件是无条件启用的，因此它们可能会对完全信任的应用程序造成损害。 在这种情况下，如果特定应用程序及其承载的内容没有安全风险，则可以禁用相应的功能控件。  
  
 功能控件由实例化 Web 浏览器 ActiveX 对象的过程应用。 因此，如果要创建可导航到不受信任的内容的独立应用程序，则应该认真考虑启用附加功能控件。  
  
> [!NOTE]
> 此建议是根据 MSHTML 和 SHDOCVW 主机安全性的一般性建议提出的。 有关详细信息，请参阅[MSHTML 主机安全常见问题解答：II 部分 I](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/)和[MSHTML 主机安全常见问题解答：II 的第二部分](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/)。  
  
 对于可执行文件，请考虑通过将注册表值设置为 1 来启用以下功能控件。  
  
|功能控件|  
|---------------------|  
|FEATURE_ACTIVEX_REPURPOSEDETECTION|  
|FEATURE_BLOCK_LMZ_IMG|  
|FEATURE_BLOCK_LMZ_OBJECT|  
|FEATURE_BLOCK_LMZ_SCRIPT|  
|FEATURE_RESTRICT_RES_TO_LMZ|  
|FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7|  
|FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG|  
|FEATURE_LOCALMACHINE_LOCKDOWN|  
|FEATURE_FORCE_ADDR_AND_STATUS|  
|FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND|  
  
 对于可执行文件，请考虑通过将注册表值设置为 0 来禁用以下功能控件。  
  
|功能控件|  
|---------------------|  
|FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT|  
  
 如果运行部分信任的 XAML 浏览器应用程序 （XBAP），该应用程序在<xref:System.Windows.Controls.WebBrowser>Windows Internet 资源管理器中包含 WPF 控件，则 WPF 在 Internet 资源管理器进程的地址空间中托管 Web 浏览器 ActiveX 控件。 由于 Web 浏览器 ActiveX 控件托管在 Internet 资源管理器过程中，因此 Internet Explorer 的所有功能控件也已为 Web 浏览器 ActiveX 控件启用。  
  
 与普通的独立应用程序相比，运行于 Internet Explorer 中的 XBAP 还将另外获得一层安全保护。 这种额外的安全性是因为 Internet 资源管理器（因此是 Web 浏览器 ActiveX 控件）默认在 Windows Vista 和 Windows 7 上以受保护模式运行。 有关受保护模式的详细信息，请参阅[在受保护模式下了解和工作 Internet 资源管理器](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/)。  
  
> [!NOTE]
> 如果您尝试运行一个 XBAP，该 XBAP 在 Firefox 中包含<xref:System.Windows.Controls.WebBrowser>WPF<xref:System.Security.SecurityException>控件，而在 Internet 区域中，将引发 。 这是由于 WPF 安全策略造成的。  
  
<a name="APTCA"></a>
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>对部分受信任的客户端应用程序禁用 APTCA 程序集  
 当托管程序集安装到全局程序集缓存 （GAC） 中时，它们将完全受信任，因为用户必须提供显式权限才能安装它们。 因为这些程序集是完全受信任的，所以只有完全受信任的托管客户端应用程序才可以使用它们。 要允许部分受信任的应用程序使用它们，必须用<xref:System.Security.AllowPartiallyTrustedCallersAttribute>（APTCA） 标记它们。 仅当程序集经过测试，可在部分信任的情况下安全执行时，才应该为其标记此特性。  
  
 但是，APTCA 程序集在安装到 GAC 后可能会表现出安全漏洞。 一旦发现安全漏洞，程序集发布者可以生成安全更新来修复现有安装上的问题，还可以阻止问题发现后进行的安装操作。 其中一个更新选项是卸载程序集，即使这可能中断使用该程序集的其他完全受信任的客户端应用程序。  
  
 WPF 提供了一种机制，通过该机制，无需卸载 APTCA 程序集，即可禁用 APTCA 程序集，以用于部分受信任的 XBAPs。  
  
 若要禁用 APTCA 程序集，必须创建一个特殊的注册表项：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 示例如下：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 此项建立 APTCA 程序集的条目。 还必须在此项中创建值来启用或禁用程序集。 下面是该值的详细信息：  
  
- 值名称 **：APTCA_FLAG**。  
  
- 值类型 **：REG_DWORD**。  
  
- 值数据 **：1**个要禁用;**0**启用。  
  
 如果必须为部分受信任的客户端应用程序禁用某程序集，可以编写一个用于创建注册表项和值的更新。  
  
> [!NOTE]
> Core .NET 框架程序集不会以这种方式禁用它们，因为它们是托管应用程序运行所必需的。 对禁用 APTCA 程序集的支持主要面向第三方应用程序。  
  
<a name="LooseContentSandboxing"></a>
## <a name="sandbox-behavior-for-loose-xaml-files"></a>宽松 XAML 文件的沙盒行为  
 松散[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]文件是仅标记的 XAML 文件，不依赖于任何代码备份、事件处理程序或特定于应用程序的程序集。 当松散[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]文件直接从浏览器导航到时，它们将基于默认 Internet 区域权限集加载到安全沙盒中。  
  
 但是，当松散[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]文件从 或<xref:System.Windows.Navigation.NavigationWindow>在独立应用程序中导航到时<xref:System.Windows.Controls.Frame>，安全行为会有所不同。  
  
 在这两种情况下，导航以[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]继承其主机应用程序权限的松散文件。 但是，从安全角度来看，此行为可能是不可取的，尤其是在由不[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]受信任的实体或未知实体生成的松散文件的情况下。 这种类型的内容称为*外部内容*，<xref:System.Windows.Controls.Frame>并且<xref:System.Windows.Navigation.NavigationWindow>可以配置为在导航到时将其隔离。 通过将**沙盒外部内容**属性设置为 true 来实现隔离，如 以下示例<xref:System.Windows.Controls.Frame>所示， <xref:System.Windows.Navigation.NavigationWindow>  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 使用此设置，外部内容将加载到不同于承载应用程序的进程的进程中。 此进程被限制在默认 Internet 区域权限集中，从而有效地将其与承载应用程序和客户端计算机隔离。  
  
> [!NOTE]
> 即使基于 WPF[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]浏览器托管基础结构<xref:System.Windows.Navigation.NavigationWindow>（<xref:System.Windows.Controls.Frame>涉及演示文稿主机进程）实现从 a 或独立应用程序中对松散文件的导航，安全级别比直接在 Windows Vista 和 Windows 7 上的 Internet 资源管理器中加载的内容（这仍通过演示主机）时略低。 这是因为使用 Web 浏览器的独立 WPF 应用程序不提供 Internet Explorer 的额外“保护模式”安全功能。  
  
<a name="BestPractices"></a>
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>用于开发可提高安全性的 WPF 应用程序的资源  
 以下是一些其他资源，可帮助开发 WPF 应用程序，以提高安全性：  
  
|区域|资源|  
|----------|--------------|  
|托管代码|[应用程序的模式和实践安全指南](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[代码访问安全性](../misc/code-access-security.md)|  
|ClickOnce|[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[WPF 部分信任安全](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>另请参阅

- [WPF 部分信任安全](wpf-partial-trust-security.md)
- [WPF 安全策略 - 平台安全性](wpf-security-strategy-platform-security.md)
- [WPF 安全策略 - 安全工程](wpf-security-strategy-security-engineering.md)
- [应用程序的模式和实践安全指南](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [代码访问安全性](../misc/code-access-security.md)
- [ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)
- [XAML 概述 (WPF)](../../desktop-wpf/fundamentals/xaml.md)
