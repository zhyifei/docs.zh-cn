---
title: 支持 .NET 应用程序部署的 Firefox 加载项
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1066332b8c5b98b5cca45e7ffbea83bd8cee8775
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>支持 .NET 应用程序部署的 Firefox 加载项
Windows Presentation Foundation (WPF) 插件 Firefox 和.NET Framework 适用于助手 Firefox 启用[!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)]、 松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，和 ClickOnce 应用程序来处理 Mozilla Firefox 浏览器。  
  
## <a name="wpf-plug-in-for-firefox"></a>WPF Firefox 插件  
 Firefox 插件 WPF 使[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]和松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]要导航到并在顶级或 Firefox 浏览器中 HTML IFRAME 运行文件。 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]是[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]可发布到 Web 服务器和中启动应用程序支持的浏览器。 松散[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]是一个仅 XAML 文件，可以导航到并显示在支持的浏览器，类似于 XML 文件。  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]插件安装适用于 Firefox 的与[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]。 窗口 7 包括[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]，但不包括[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Firefox 插件。 无法安装[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]在 Windows 7 上 Firefox 插件。  
  
 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]不包括[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Firefox 插件。 但是，如果这两个[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]和[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]是安装，使用安装插件 Firefox WPF [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]。 因此[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]因为 WPF 主机将始终加载框架的正确版本，仍将运行应用程序。 有关详细信息，请参阅[WPF 主机 (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)。  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant for Firefox  
 .NET Framework 适用于助手 Firefox 允许独立 ClickOnce 应用程序从 Firefox 浏览器运行。 .NET Framework 助手 Firefox 函数的相同安装之前和之后 Firefox 浏览器。 Firefox 浏览器启动时和[!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]是 Firefox 安装，查找并安装.NET Framework 助手 Firefox。 用户可以配置.NET Framework 适用于助手 Firefox 以执行以下操作：  
  
-   运行 ClickOnce 应用程序之前进行提示。  
  
-   报告所有已安装的版本的.NET Framework 或只需最新版本。  
  
 .NET Framework 助手对于 Firefox 是附带[!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]。 有关为 Firefox 删除.NET Framework 助手的信息，请参阅[如何删除.NET Framework 助手 Firefox](http://go.microsoft.com/fwlink/?LinkId=177944)。  
  
## <a name="see-also"></a>请参阅  
 [部署 WPF 应用程序](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)  
 [WPF XAML Browser Applications Overview](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)（WPF XAML 浏览器应用程序概述）  
 [检测是否安装了适用于 Firefox 的 WPF 插件](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
