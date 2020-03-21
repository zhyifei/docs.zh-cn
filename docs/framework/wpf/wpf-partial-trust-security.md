---
title: 部分信任安全性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- partial trust security [WPF]
- detecting permissions [WPF]
- security settings for Internet Explorer [WPF]
- partial trust applications [WPF], debugging
- permissions [WPF], managing
- debugging partial trust applications [WPF]
- permissions [WPF], detecting
- feature security requirements [WPF]
- managing permissions [WPF]
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
ms.openlocfilehash: 99c7d9cfae2b137053ca77d9e3d7055b4674ce5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174571"
---
# <a name="wpf-partial-trust-security"></a>WPF 部分信任安全
<a name="introduction"></a>一般情况下，应该限制 Internet 应用程序直接访问关键系统资源，防止恶意损坏。 默认情况下，HTML 和客户端脚本语言无法访问关键系统资源。 由于 Windows 演示文稿基础 （WPF） 浏览器托管的应用程序可以从浏览器启动，因此它们应符合一组类似的限制。 要实施这些限制，WPF 依赖于代码访问安全性 （CAS） 和 ClickOnce（请参阅[WPF 安全策略 - 平台安全](wpf-security-strategy-platform-security.md)）。 默认情况下，浏览器托管的应用程序请求 Internet 区域 CAS 权限集，无论它们是从 Internet、本地 Intranet 还是本地计算机启动。 如果应用程序的运行权限小于完整权限集，则说明该应用程序正在部分信任环境下运行。  
  
 WPF 提供了多种支持，以确保尽可能多的功能可以在部分信任中安全使用，并且与 CAS 一起为部分信任编程提供了额外的支持。  
  
 本主题包含以下各节：  
  
- [WPF 功能部分信任支持](#WPF_Feature_Partial_Trust_Support)  
  
- [部分信任编程](#Partial_Trust_Programming)  
  
- [管理权限](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>
## <a name="wpf-feature-partial-trust-support"></a>WPF 功能部分信任支持  
 下表列出了 Windows 演示文稿基础 （WPF） 的高级功能，这些功能可以在 Internet 区域权限集的范围内安全使用。  
  
 表 1：在部分信任环境中安全的 WPF 功能  
  
|功能区|Feature|  
|------------------|-------------|  
|常规|浏览器窗口<br /><br /> 源站点访问<br /><br /> IsolatedStorage（512KB 限制）<br /><br /> UIAutomation 提供程序<br /><br /> 命令<br /><br /> 输入法编辑器 (IME)<br /><br /> 触笔和墨迹<br /><br /> 使用鼠标捕获和移动事件模拟的拖/放<br /><br /> OpenFileDialog<br /><br /> XAML 反序列化（通过 XamlReader.Load）|  
|Web 集成|浏览器下载对话框<br /><br /> 顶级用户启动的导航<br /><br /> mailto:links<br /><br /> 统一资源标识符参数<br /><br /> HTTPWebRequest<br /><br /> IFRAME 中托管的 WPF 内容<br /><br /> 使用框架托管同一站点 HTML 页<br /><br /> 使用 WebBrowser 托管同一站点 HTML 页<br /><br /> Web 服务 (ASMX)<br /><br /> Web 服务（使用 Windows Communication Foundation）<br /><br /> 脚本编写<br /><br /> 文档对象模型|  
|视觉对象|2D 和 3D<br /><br /> 动画<br /><br /> 媒体（源站点和跨域）<br /><br /> 图像处理/音频/视频|  
|阅读|流文档<br /><br /> XPS 文档<br /><br /> 嵌入式字体与系统字体<br /><br /> CFF 字体与 TrueType 字体|  
|编辑|拼写检查<br /><br /> RichTextBox<br /><br /> 纯文本和墨迹剪贴板支持<br /><br /> 用户启动的粘贴<br /><br /> 复制选定内容|  
|控制|常规控件|  
  
 下表在高级别上介绍 WPF 功能。 有关详细信息，Windows SDK 将记录 WPF 中每个成员所需的权限。 此外，以下功能含有部分信任执行的相关详细信息，其中包括特殊注意事项。  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]（请参阅[XAML 概述 （WPF）。](../../desktop-wpf/fundamentals/xaml.md)  
  
- 弹出窗口（参见<xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>）。  
  
- 拖放（请参阅[拖放概述](./advanced/drag-and-drop-overview.md)）。  
  
- 剪贴板（<xref:System.Windows.Clipboard?displayProperty=nameWithType>参见 ）。  
  
- 成像（参见<xref:System.Windows.Controls.Image?displayProperty=nameWithType>）。  
  
- 序列化（参见<xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>。  
  
- 打开文件对话框（请参阅<xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>）。  
  
 下表概述了在 Internet 区域权限集的限制内运行不安全的 WPF 功能。  
  
 表 2：在部分信任环境中不安全的 WPF 功能  
  
|功能区|Feature|  
|------------------|-------------|  
|常规|窗口（应用程序定义的窗口和对话框）<br /><br /> SaveFileDialog<br /><br /> 文件系统<br /><br /> 注册表访问<br /><br /> 拖放<br /><br /> XAML 序列化（通过 XamlWriter.Save）<br /><br /> UIAutomation 客户端<br /><br /> 源窗口访问 (HwndHost)<br /><br /> 完全语音支持<br /><br /> Windows 窗体互操作性|  
|视觉对象|位图效果<br /><br /> 图像编码|  
|编辑|RTF 格式剪贴板<br /><br /> 完全 XAML 支持|  
  
<a name="Partial_Trust_Programming"></a>
## <a name="partial-trust-programming"></a>部分信任编程  
 对于 XBAP 应用程序，超出默认权限集的代码将具有不同的行为，具体取决于安全区域。 在某些情况下，用户会在尝试安装它时收到警告。 用户可以选择继续或取消安装。 下表描述每个安全区域的应用程序的行为，以及为了使应用程序接收完全信任而必须执行的操作。  
  
|安全区域|行为|获取完全信任|  
|-------------------|--------------|------------------------|  
|本地计算机|自动完全信任|无需采取任何措施。|  
|Intranet 和受信任的站点|提示完全信任|使用证书对 XBAP 进行签名，以便用户在提示中看到源。|  
|Internet|失败，并显示“未授予信任”|使用证书对 XBAP 进行签名。|  
  
> [!NOTE]
> 上表中描述的行为针对不遵循 ClickOnce 受信任部署模型的完全信任 XBAP。  
  
 通常，超出允许权限的代码可能是在独立应用程序和浏览器托管的应用程序之间共享的公用代码。 CAS 和 WPF 提供了几种管理此方案的技术。  
  
<a name="Detecting_Permissions_using_CAS"></a>
### <a name="detecting-permissions-using-cas"></a>使用 CAS 检测权限  
 在某些情况下，库程序集中的共享代码可能同时由独立应用程序和 XBAP 使用。 这时，代码执行的功能所需要的权限可能超出应用程序的授权权限集允许的权限。 您的应用程序可以通过使用 Microsoft .NET 框架安全性来检测它是否具有特定权限。 具体而言，它可以通过在所需权限的实例上调用方法来<xref:System.Security.CodeAccessPermission.Demand%2A>测试它是否具有特定权限。 以下示例对此进行了演示，示例中的代码查询其是否能够将文件保存到本地磁盘：  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 如果应用程序没有所需的权限，则调用 将<xref:System.Security.CodeAccessPermission.Demand%2A>引发安全异常。 如果没有引发异常，则表示已授予该权限。 `IsPermissionGranted`封装此行为并返回`true`或`false`根据需要返回。  
  
<a name="Graceful_Degradation_of_Functionality"></a>
### <a name="graceful-degradation-of-functionality"></a>功能下降  
 对可从不同区域执行的代码而言，能够检测代码是否具有完成所需操作的权限是很有意义的。 能够检测区域固然不错，但如果能够为用户提供替代方法，则要好得多。 例如，完全信任应用程序通常使用户能够在所需的任何位置创建文件，而部分信任应用程序只能在独立存储中创建文件。 如果用于创建文件的代码存在于完全信任（独立）应用程序和部分信任（浏览器托管的）应用程序共享的程序集中，并且这两个应用程序都希望用户能够创建文件，则共享代码应首先检测其是在部分信任环境还是完全信任环境中运行，然后才能在适当的位置创建文件。 下面的代码对这两种情况进行了演示。  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 在很多情况下，应该能够找到部分信任替代方法。  
  
 在受控环境中（如 Intranet），自定义托管框架可以跨客户端安装到全局程序集缓存 （GAC）。 这些库可以执行需要完全信任的代码，并且只能使用<xref:System.Security.AllowPartiallyTrustedCallersAttribute>允许部分信任的应用程序引用（有关详细信息，请参阅[安全和](security-wpf.md) [WPF 安全策略 - 平台安全](wpf-security-strategy-platform-security.md)）。  
  
<a name="Browser_Host_Detection"></a>
### <a name="browser-host-detection"></a>浏览器主机检测  
 当您需要按权限进行检查时，使用 CAS 检查权限是一种合适的技术。 然而，这一技巧依赖于在正常处理过程中捕获异常（通常不鼓励这样做），并且可能导致性能问题。 相反，如果您的 XAML 浏览器应用程序 （XBAP） 仅在 Internet 区域沙盒中运行，则可以使用<xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType>属性，该属性对于 XAML 浏览器应用程序 （XBAP） 返回 true。  
  
> [!NOTE]
> <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A>仅区分应用程序是否在浏览器中运行，而不是区分应用程序正在使用哪个权限集。  
  
<a name="Managing_Permissions"></a>
## <a name="managing-permissions"></a>管理权限  
 默认情况下，XBAP 以部分信任（默认 Internet 区域权限集）运行。 但是，根据应用程序的要求，可以更改默认的权限集。 例如，如果从本地 Intranet 启动 XBAP，则可以利用增加的权限集，如下表所示。  
  
 表 3：LocalIntranet 和 Internet 权限  
  
|权限|Attribute|LocalIntranet|Internet|  
|----------------|---------------|-------------------|--------------|  
|DNS|访问 DNS 服务器|是|否|  
|环境变量|读取|是|否|  
|文件对话框|打开|是|是|  
|文件对话框|非受限|是|否|  
|独立存储|按用户隔离程序集|是|否|  
|独立存储|未知隔离|是|是|  
|独立存储|无限制用户配额|是|否|  
|媒体|安全音频、视频和图像|是|是|  
|打印|默认打印|是|否|  
|打印|安全打印|是|是|  
|反射|发出|是|否|  
|安全性|托管代码执行|是|是|  
|安全性|声明授予的权限|是|否|  
|用户界面|非受限|是|否|  
|用户界面|安全顶级窗口|是|是|  
|用户界面|自己的剪贴板|是|是|  
|Web 浏览器|HTML 中的安全框架导航|是|是|  
  
> [!NOTE]
> 如果由用户启动，则剪切和粘贴只允许以部分信任方式执行。  
  
 如果需要增加权限，则需要更改项目设置和 ClickOnce 应用程序清单。 有关详细信息，请参阅 [WPF XAML 浏览器应用程序概述](./app-development/wpf-xaml-browser-applications-overview.md)。 以下各个文档可能也会有帮助。  
  
- [Mage.exe （清单生成和编辑工具）](../tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
- [MageUI.exe （清单生成和编辑工具，图形客户端）](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)。  
  
- [保护 ClickOnce 应用程序](/visualstudio/deployment/securing-clickonce-applications)。  
  
 如果您的 XBAP 需要完全信任，则可以使用相同的工具来增加请求的权限。 尽管 XBAP 仅在本地计算机上安装并从 Intranet 上启动时才会获得完全信任，但 Intranet 或来自浏览器受信任或允许站点中列出的 URL。 如果从 Intranet 或受信任站点安装应用程序，则用户会收到标准 ClickOnce 提示，通知用户提升了权限。 用户可以选择继续或取消安装。  
  
 或者，可以使用 ClickOnce 受信任部署模型从任何安全区域中进行完全信任部署。 有关详细信息，请参阅[受信任的应用程序部署概述](/visualstudio/deployment/trusted-application-deployment-overview)[和安全](security-wpf.md)。  
  
## <a name="see-also"></a>另请参阅

- [安全性](security-wpf.md)
- [WPF 安全策略 - 平台安全性](wpf-security-strategy-platform-security.md)
- [WPF 安全策略 - 安全工程](wpf-security-strategy-security-engineering.md)
