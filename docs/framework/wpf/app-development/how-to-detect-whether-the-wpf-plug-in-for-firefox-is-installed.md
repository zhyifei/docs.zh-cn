---
title: 如何：检测是否已安装 Firefox 的 WPF 插件
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
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b58abda33aa48372e4642dca48599867f389045
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>如何：检测是否已安装 Firefox 的 WPF 插件
Windows Presentation Foundation (WPF) 插件 Firefox 使[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]和松散的 XAML 文件中 Mozilla Firefox 浏览器运行。 本主题提供了用 HTML 和 JavaScript，管理员可以使用以确定是否安装了插件 Firefox WPF 编写的脚本。  
  
> [!NOTE]
>  有关安装、 部署和检测的详细信息[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]，请参阅[安装.NET Framework 为开发人员](../../../../docs/framework/install/guide-for-developers.md)。  
  
## <a name="example"></a>示例  
 当[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]是安装，客户端计算机配置很插件 WPF Firefox。 以下示例脚本检查插件的 wpf Firefox，然后显示相应的状态消息。  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 如果 Firefox 插件的 wpf 的检查成功，将显示以下状态消息：  
  
 `The WPF plug-in for Firefox is installed.`  
  
 否则，显示以下状态消息：  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a>请参阅  
 [检测是否安装了 .NET Framework 3.0](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [检测是否安装了 .NET Framework 3.5](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [WPF XAML Browser Applications Overview](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)（WPF XAML 浏览器应用程序概述）
