---
title: "如何：检测是否已安装 Firefox 的 WPF 插件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3012afc118420a83c869785d26c28f1eee969cb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="772e9-102">如何：检测是否已安装 Firefox 的 WPF 插件</span><span class="sxs-lookup"><span data-stu-id="772e9-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="772e9-103">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]插件 Firefox 可让[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]和松散的 XAML 文件中 Mozilla Firefox 浏览器运行。</span><span class="sxs-lookup"><span data-stu-id="772e9-103">The [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="772e9-104">本主题提供了用 HTML 和 JavaScript，管理员可以使用以确定是否安装了插件 Firefox WPF 编写的脚本。</span><span class="sxs-lookup"><span data-stu-id="772e9-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="772e9-105">有关安装、 部署和检测的详细信息[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]，请参阅[安装.NET Framework 为开发人员](../../../../docs/framework/install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="772e9-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="772e9-106">示例</span><span class="sxs-lookup"><span data-stu-id="772e9-106">Example</span></span>  
 <span data-ttu-id="772e9-107">当[!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]是安装，客户端计算机配置很插件 WPF Firefox。</span><span class="sxs-lookup"><span data-stu-id="772e9-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="772e9-108">以下示例脚本检查插件的 wpf Firefox，然后显示相应的状态消息。</span><span class="sxs-lookup"><span data-stu-id="772e9-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
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
  
 <span data-ttu-id="772e9-109">如果 Firefox 插件的 wpf 的检查成功，将显示以下状态消息：</span><span class="sxs-lookup"><span data-stu-id="772e9-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="772e9-110">否则，显示以下状态消息：</span><span class="sxs-lookup"><span data-stu-id="772e9-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="772e9-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="772e9-111">See Also</span></span>  
 [<span data-ttu-id="772e9-112">检测是否安装了 .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="772e9-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="772e9-113">检测是否安装了 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="772e9-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 <span data-ttu-id="772e9-114">[WPF XAML Browser Applications Overview](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)（WPF XAML 浏览器应用程序概述）</span><span class="sxs-lookup"><span data-stu-id="772e9-114">[WPF XAML Browser Applications Overview](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)</span></span>
