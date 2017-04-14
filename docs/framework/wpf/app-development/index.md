---
title: "应用程序开发 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "应用程序开发 [WPF], 关于"
  - "WPF, 关于应用程序开发"
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 应用程序开发
<a name="introduction"></a> [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 是一种演示框架，可用于开发以下类型的应用程序：  
  
-   独立应用程序（传统风格的 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 应用程序，以可执行程序集的形式生成，安装在客户端计算机上并从客户端计算机上运行）。  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]（由导航页面构成的应用程序，这些页面以可执行程序集的形式生成，由 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 和 Mozilla Firefox 这类 Web 浏览器承载）。  
  
-   自定义控件库（包含可重用控件的不可执行程序集）。  
  
-   类库（包含可重用类的不可执行程序集）。  
  
> [!NOTE]
>  强烈建议不要在 Windows 服务中使用 WPF 类型。  如果尝试在 Windows 服务中使用这些功能，则这些功能可能无法按预期方式工作。  
  
 为了创建此组应用程序，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 实现了大量服务。  本主题概述这些服务并说明从何处可以获得更多信息。  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Application_Management"></a>   
## 应用程序管理  
 可执行 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序通常需要一组核心功能，包括：  
  
-   创建和管理通用应用程序基础结构（包括创建入口点方法和 Windows 消息循环，以接收系统和输入消息）。  
  
-   跟踪应用程序的生命周期并与之交互。  
  
-   检索和处理命令行参数。  
  
-   共享应用程序范围的属性和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 资源。  
  
-   检测和处理未经处理的异常。  
  
-   返回退出代码。  
  
-   管理独立应用程序中的窗口。  
  
-   跟踪 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 以及带有导航窗口和框架的独立应用程序中的导航。  
  
 这些功能通过 <xref:System.Windows.Application> 类来实现，您可以使用应用程序定义将该类添加到您的应用程序中。  
  
 有关更多信息，请参见[应用程序管理概述](../../../../docs/framework/wpf/app-development/application-management-overview.md)。  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## WPF 应用程序资源、内容和数据文件  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 支持三种不可执行的数据文件：资源、内容和数据，扩展了 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] 中对嵌入资源的核心支持。有关更多信息，请参见 [WPF 应用程序资源、内容和数据文件](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)。  
  
 对 WPF 不可执行数据文件的支持的关键所在就是能够使用唯一的 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 来标识和加载这些文件。有关更多信息，请参见 [WPF 中的 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)。  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## 窗口和对话框  
 用户通过窗口与 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 独立应用程序进行交互。  窗口的用途是承载应用程序内容并公开通常允许用户与内容交互的应用程序功能。  在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，窗口通过 <xref:System.Windows.Window> 类进行封装，该类支持：  
  
-   创建和显示窗口。  
  
-   建立所有者窗口\/附属窗口关系。  
  
-   配置窗口外观（例如，大小、位置、图标、标题栏文本和边框）。  
  
-   跟踪窗口的生命周期并与之交互。  
  
 有关更多信息，请参见 [WPF Windows 概述](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)。  
  
 <xref:System.Windows.Window> 支持创建一个特殊类型的窗口（即对话框）。  既可以创建模式类型的对话框，也可以创建无模式类型的对话框。  
  
 为了方便起见，还为了在应用程序中获得可重用性并保持一致的用户体验，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 公开了三个常用的 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] 对话框：<xref:Microsoft.Win32.OpenFileDialog>、<xref:Microsoft.Win32.SaveFileDialog> 和 <xref:System.Windows.Controls.PrintDialog>。  
  
 消息框是一种特殊的对话框，用于向用户显示重要的文本信息，并询问简单的“是\/否\/确定\/取消”问题。  可以使用 <xref:System.Windows.MessageBox> 类创建并显示消息框。  
  
 有关更多信息，请参见[对话框概述](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)。  
  
<a name="Navigation"></a>   
## 导航  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 支持使用页面 \(<xref:System.Windows.Controls.Page>\) 和超链接 \(<xref:System.Windows.Documents.Hyperlink>\) 进行 Web 风格的导航。  可以通过多种方式实现导航，包括：  
  
-   由 Web 浏览器承载的独立页面。  
  
-   编译到 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]（由 Web 浏览器承载）中的页面。  
  
-   编译到独立应用程序中并由导航窗口 \(<xref:System.Windows.Navigation.NavigationWindow>\) 承载的页面。  
  
-   由帧 \(<xref:System.Windows.Controls.Frame>\) 承载的页面，可以由独立页面承载，或编译到 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 或独立应用程序中的页面。  
  
 为了便于导航，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 实现了下列功能：  
  
-   <xref:System.Windows.Navigation.NavigationService>，用于处理导航请求的共享导航引擎，由 <xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow> 和 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 使用以支持应用程序内部的导航。  
  
-   用于启动导航的导航方法。  
  
-   用于跟踪导航的生命周期并与之交互的导航事件。  
  
-   使用日记记住后退和前进导航，也可以对日记进行检查和操作。  
  
 有关信息，请参见[导航概述](../../../../docs/framework/wpf/app-development/navigation-overview.md)。  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 还支持一种特殊的导航，称为结构化导航。  结构化导航可用于调用一个或多个页面，这些页面通过与调用函数一致的结构化和可预测方式返回数据。  此功能依赖于 <xref:System.Windows.Navigation.PageFunction%601> 类，[结构化导航概述](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)中对该类进行了进一步介绍。  <xref:System.Windows.Navigation.PageFunction%601> 还用于简化复杂导航拓扑的创建，[导航拓扑概述](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)中对导航拓扑进行了介绍。  
  
<a name="Hosting"></a>   
## 承载  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 可以由 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 或 Firefox 承载。  每个承载模型都有其自己的一系列注意事项和局限性，[宿主](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)中对此进行了介绍。  
  
<a name="Build_and_Deploy"></a>   
## 生成和部署  
 尽管可以使用命令行编译器从命令提示符中生成简单的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序，但 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 与 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 进行了集成，以便为简化开发和生成过程提供更多支持。  有关更多信息，请参见[生成 WPF 应用程序](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)。  
  
 根据您生成的应用程序的类型，可以选择一种或多种部署方式。  有关更多信息，请参见[部署 WPF 应用程序](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)。  
  
<a name="related_topics"></a>   
## 相关主题  
  
|标题|说明|  
|--------|--------|  
|[应用程序管理概述](../../../../docs/framework/wpf/app-development/application-management-overview.md)|提供 <xref:System.Windows.Application> 类的概述，包括管理应用程序生存期、窗口、应用程序资源和导航。|  
|[WPF 中的窗口](../../../../docs/framework/wpf/app-development/windows-in-wpf-applications.md)|提供有关如何在应用程序中管理窗口的详细信息，包括如何使用 <xref:System.Windows.Window> 类和对话框。|  
|[导航概述](../../../../docs/framework/wpf/app-development/navigation-overview.md)|概述如何管理应用程序页面之间的导航。|  
|[宿主](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)|提供 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 的概述。|  
|[生成和部署](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)|介绍如何生成和部署 WPF 应用程序。|  
|[Visual Studio 2015 中的 WPF 简介](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)|介绍 WPF 的主要功能。|  
|[演练：开始使用 WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|演示如何使用页面导航、布局、控件、图像、样式和绑定创建 WPF 应用程序的演练。|