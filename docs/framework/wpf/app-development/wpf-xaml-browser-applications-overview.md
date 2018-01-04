---
title: "WPF XAML 浏览器应用程序概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XBAP [WPF], XAML browser application
- WPF XAML browser applications (XBAP)
- XAML browser applications (XBAP)
- browser-hosted applications [WPF]
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c894d431aa31e32b4a8cb7ff02d39d5aa5e95381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-xaml-browser-applications-overview"></a>WPF XAML 浏览器应用程序概述
<a name="introduction"></a>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]将组合的 Web 应用程序和丰富的客户端应用程序的功能。 与 Web 应用程序类似，可以将 XBAP 部署到 Web 服务器并从 Internet Explorer 或 Firefox 启动。 与丰富客户端应用程序类似，XBAP 可以充分利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的功能。 开发 XBAP 也与开发丰富客户端类似。 本主题提供简单、高级的 XBAP 开发简介，并介绍 XBAP 开发与标准的丰富客户端开发的不同之处。  
  
 本主题包含以下各节：  
  
-   [创建新的 XAML 浏览器应用程序 (XBAP)](#creating_a_new_xaml_browser_application_xbap)  
  
-   [部署 XBAP](#deploying_a_xbap)  
  
-   [与宿主网页通信](#communicating_with_the_host_web_page)  
  
-   [XBAP 安全注意事项](#xbap_security_considerations)  
  
-   [XBAP 启动时间性能注意事项](#xbap_start_time_performance_considerations)  
  
<a name="creating_a_new_xaml_browser_application_xbap"></a>   
## <a name="creating-a-new-xaml-browser-application-xbap"></a>创建新的 XAML 浏览器应用程序 (XBAP)  
 新建 XBAP 项目的最简单方法是使用 [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]。 创建新项目时，从模板列表中选择“WPF 浏览器应用程序”。 有关详细信息，请参阅[如何：创建新的 WPF 浏览器应用程序项目](http://msdn.microsoft.com/en-us/72ef4d90-e163-42a1-8df0-ea7ccfd1901f)。  
  
 运行 XBAP 项目时，它将在浏览器窗口而不是在单独的窗口中打开。 在 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 中调试 XBAP 时，应用程序将通过 Internet 区域权限运行，因此如果超出这些权限，将引发安全异常。 有关详细信息，请参阅[安全性](../../../../docs/framework/wpf/security-wpf.md)和 [WPF 部分信任安全性](../../../../docs/framework/wpf/wpf-partial-trust-security.md)。  
  
> [!NOTE]
>  如果不使用 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 开发或者想要了解有关项目文件的详细信息，请参阅[生成 WPF 应用程序](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)。  
  
<a name="deploying_a_xbap"></a>   
## <a name="deploying-an-xbap"></a>部署 XBAP  
 生成 XBAP 时，输出将包括以下三个文件：  
  
|文件|描述|  
|----------|-----------------|  
|可执行文件 (.exe)|此文件包含已编译的代码且具有 .exe 扩展名。|  
|应用程序清单 (.manifest)|此文件包含与应用程序关联的元数据且具有 .manifest 扩展名。|  
|部署清单 (.xbap)|此文件包含 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 用于部署应用程序的信息，且具有 .xbap 扩展名。|  
  
 将 XBAP 部署到 Web 服务器，例如 [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] 或更高版本。 不需要在 Web 服务器上安装 [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]，但是需要注册 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] 类型和文件扩展名。 有关详细信息，请参阅[配置 IIS 5.0 和 IIS 6.0 以部署 WPF 应用程序](../../../../docs/framework/wpf/app-development/how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md)。  
  
 若要将 XBAP 准备好进行部署，请将 .exe 和关联的清单复制到 Web 服务器。 创建包含超链接的 HTML 页以打开部署清单，即扩展名为 .xbap 的文件。 用户单击指向 .xbap 文件的链接时，[!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 将自动处理应用程序的下载和启动机制。 下面的代码示例显示包含指向 XBAP 的超链接的 HTML 页面。  
  
```html
<html>   
    <head></head>  
    <body>   
        <a href="XbapEx.xbap">Click this link to launch the application</a>  
    </body>   
</html>  
```  
  
 还可以在网页框架中承载 XBAP。 创建具有一个或多个框架的网页。 将框架的源属性设置为部署清单文件。 如果想要使用内置机制在宿主网页和 XBAP 之间进行通信，则必须在框架中承载应用程序。 下面的示例代码演示了具有两个框架的 HTML 页面，第二个框架的源设置为 XBAP。  
  
```html
<html>   
    <head>
        <title>A page with frames</title>
    </head>  
    <frameset cols="50%,50%">   
        <frame src="introduction.htm">   
        <frame src="XbapEx.xbap">   
    </frameset>   
</html>  
```  
  
### <a name="clearing-cached-xbaps"></a>清除缓存的 XBAP  
 在某些情况下，重新生成并启动 XBAP 后，可能会发现打开了早期版本的 XBAP。 例如，当 XBAP 程序集版本号是静态的，并从命令行启动 XBAP 时，可能会出现此行为。 在这种情况下，由于缓存的版本（以前启动的版本）和新版本的版本号相同，因此不会下载 XBAP 的新版本。 而会加载缓存的版本。  
  
 在这些情况下，可以在命令提示符处使用 **Mage** 命令（随 Visual Studio 或 [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] 一起安装）删除缓存的版本。 以下命令可清除应用程序缓存。  
  
 ```console
 Mage.exe -cc
 ```
  
 此命令可保证启动最新版本的 XBAP。 在 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 中调试应用程序时，应启动最新版本的 XBAP。 一般情况下，应在每次生成时更新部署版本号。 有关 Mage 的详细信息，请参阅 [Mage.exe（清单生成和编辑工具）](../../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)。  
  
<a name="communicating_with_the_host_web_page"></a>   
## <a name="communicating-with-the-host-web-page"></a>与宿主网页通信  
 当在 HTML 框架中承载应用程序时，可以与包含 XBAP 的网页进行通信。 执行此操作通过检索<xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A>属性<xref:System.Windows.Interop.BrowserInteropHelper>。 此属性返回一个表示 HTML 窗口的脚本对象。 然后可以通过使用常规的点语法访问 [window object](http://go.microsoft.com/fwlink/?LinkId=160274)（window 对象）上的属性、方法和事件。 还可以访问脚本方法和全局变量。 以下示例演示如何检索脚本对象和关闭浏览器。  
  
 [!code-csharp[XbapBrowserInterop#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]  
  
### <a name="debugging-xbaps-that-use-hostscript"></a>调试使用 HostScript 的 XBAP  
 如果你 XBAP 使用<xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A>对象进行通信的 HTML 窗口中，有两个必须指定的设置来运行和调试中的应用程序[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]。 应用程序必须有权访问其源站点，并且必须使用包含 XBAP 的 HTML 页启动应用程序。 以下步骤介绍如何检查这两个设置：  
  
1.  在 Visual Studio 中，打开项目属性。  
  
2.  在“安全性”选项卡上单击“高级”。  
  
     将显示“高级安全设置”对话框。  
  
3.  请确保选中“授予应用程序对其源站点的访问权”复选框，然后单击“确定”。  
  
4.  在“调试”选项卡上，选择“使用 URL 启动浏览器”选项，然后指定包含 XBAP 的 HTML 页的 URL。  
  
5.  在 Internet Explorer 中，单击“工具”按钮，然后选择“Internet 选项”。  
  
     将显示“Internet 选项”对话框。  
  
6.  单击“高级”选项卡。  
  
7.  在“安全性”下面的“设置”列表中，选中“允许活动内容在我的计算机上的文件中运行”复选框。  
  
8.  单击 **“确定”**。  
  
     重启 Internet Explorer 后更改才会生效。  
  
> [!CAUTION]
>  在 Internet Explorer 中启用活动内容可能会给计算机带来风险。 有关详细信息，请参阅 [Internet Explorer 中的安全和隐私功能](http://go.microsoft.com/fwlink/?LinkId=179286)。 如果不想更改 Internet Explorer 安全设置，则可以从服务器启动 HTML 页，并将 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 调试器附加到进程。  
  
<a name="xbap_security_considerations"></a>   
## <a name="xbap-security-considerations"></a>XBAP 安全注意事项  
 通常在被限制到 Internet 区域权限集的部分信任的安全沙盒中执行 XBAP。 因此，实现必须支持 Internet 区域中所支持的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素的子集，或者必须提升应用程序的权限。 有关详细信息，请参阅[安全性](../../../../docs/framework/wpf/security-wpf.md)。  
  
 当你使用<xref:System.Windows.Controls.WebBrowser>内部应用程序，WPF 中的控件实例化的本机 WebBrowser ActiveX 控件。 如果应用程序是 Internet Explorer 中运行的部分信任的 XBAP，则 ActiveX 控件会在 Internet Explorer 进程的专用线程中运行。 因此，存在以下限制：  
  
-   <xref:System.Windows.Controls.WebBrowser>控件应提供类似于主机浏览器中，包括安全限制的行为。 可以通过 Internet Explorer 安全设置控制这些安全限制中的某些限制。 有关详细信息，请参阅[安全性](../../../../docs/framework/wpf/security-wpf.md)。  
  
-   在 HTML 页中跨域加载 XBAP 时，将引发异常。  
  
-   输入位于单独的线程与 WPF <xref:System.Windows.Controls.WebBrowser>，因此无法截获键盘输入，并不共享的输入法状态。  
  
-   由于 ActiveX 控件在另一个线程上运行，导航的计时或顺序可能有所不同。 例如，并不总是通过启动另一个导航请求来取消到某页的导航。  
  
-   自定义 ActiveX 控件可能会在通信方面出现问题，因为 WPF 应用程序在另一个线程上运行。  
  
-   <xref:System.Windows.Interop.HwndHost.MessageHook>不会引发因为<xref:System.Windows.Interop.HwndHost>无法在另一个线程或进程中运行的窗口的子类。  
  
### <a name="creating-a-full-trust-xbap"></a>创建完全信任的 XBAP  
 如果 XBAP 需要完全信任，则可以更改项目以启用此权限。 以下步骤介绍如何启用完全信任：  
  
1.  在 Visual Studio 中，打开项目属性。  
  
2.  在“安全性”选项卡上，选择“这是完全可信的应用程序”选项。  
  
 此设置将进行以下更改：  
  
-   在项目文件中，将 `<TargetZone>` 元素值更改为 `Custom`。  
  
-   在应用程序清单 (app.manifest) 中，将 `Unrestricted="true"` 特性添加到 `PermissionSet` 元素。  
  
    ```xml
    <PermissionSet class="System.Security.PermissionSet"   
                   version="1"   
                   ID="Custom"   
                   SameSite="site"   
                   Unrestricted="true" />  
    ```  
  
### <a name="deploying-a-full-trust-xbap"></a>部署完全信任的 XBAP  
 部署不遵循 ClickOnce 受信任部署模型的完全信任的 XBAP 时，用户运行该应用程序时的行为将取决于安全区域。 在某些情况下，用户会在尝试安装它时收到警告。 用户可以选择继续或取消安装。 下表描述每个安全区域的应用程序的行为，以及为了使应用程序接收完全信任而必须执行的操作。  
  
|安全区域|行为|获取完全信任|  
|-------------------|--------------|------------------------|  
|本地计算机|自动完全信任|无需执行任何操作。|  
|Intranet 和受信任的站点|提示完全信任|使用证书对 XBAP 进行签名，以便用户在提示中看到源。|  
|Internet|失败，并显示“未授予信任”|使用证书对 XBAP 进行签名。|  
  
> [!NOTE]
>  上表中描述的行为针对的是不遵循 ClickOnce 受信任部署模型的完全信任的 XBAP。  
  
 建议使用 ClickOnce 受信任部署模型部署完全信任的 XBAP。 此模型允许自动向 XBAP 授予完全信任（与安全区域无关），这样用户便不会收到提示。 作为此模型的一部分，必须使用来自受信任发行者提供的证书来对应用程序进行签名。 有关详细信息，请参阅[受信任的应用程序部署概述](/visualstudio/deployment/trusted-application-deployment-overview)和 [Introduction to Code Signing](http://go.microsoft.com/fwlink/?LinkId=166327)（代码签名简介）。  
  
<a name="xbap_start_time_performance_considerations"></a>   
## <a name="xbap-start-time-performance-considerations"></a>XBAP 启动时间性能注意事项  
 XBAP 性能的一个重要方面是其启动时间。 如果 XBAP 是要加载的第一个 WPF 应用程序，则冷启动时间可能为十秒或更长。 这是因为进度页面由 WPF 呈现，且 CLR 和 WPF 都必须冷启动才能显示应用程序。  
  
 在 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] 中启动时，通过在部署周期早期显示未托管进度页可以缩短 XBAP 的冷启动时间。 启动应用程序后几乎会立即显示进度页，因为它由本机宿主代码显示，并以 HTML 格式呈现。  
  
 此外，改进的 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 下载序列并发最多可将启动时间缩短 10%。 当 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 下载并验证清单后，将启动应用程序下载并开始更新进度栏。  
  
## <a name="see-also"></a>请参阅  
 [将 Visual Studio 配置为通过调试 XAML 浏览器应用程序来调用 Web 服务](../../../../docs/framework/wpf/app-development/configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)  
 [部署 WPF 应用程序](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
