---
title: IWpfHostSupport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a516d5917c2106bc83842befac9b506312fcce1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
托管应用程序[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]内容 PresentationHost.exe 通过实现此接口可提供的主机和 PresentationHost.exe 之间的集成点。  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]例如 Web 浏览器的应用程序可以承载[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]内容，包括[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]和松散 XAML。 到主机[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]内容，[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]应用程序创建的实例[WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=97911)。 要进行承载，[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]创建 PresentationHost.exe，提供所承载的一个实例[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]到的主机中的显示内容[WebBrowser 控件](http://go.microsoft.com/fwlink/?LinkId=97911)。  
  
 由启用的集成`IWpfHostSupport`允许 PresentationHost.exe 到：  
  
-   发现和与主机应用程序感兴趣的原始输入设备 （人机接口设备） 注册。  
  
-   主机应用程序的已注册的原始输入的设备和适当的消息转发从接收输入的消息。  
  
-   查询进度和错误的自定义用户界面的主机应用程序。  
  
> [!NOTE]
>  此 API 预期仅支持在本地客户端计算机上使用  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|默认情况下，PresentationHost.exe 提供其自己的部署进度和部署错误部署 WPF 内容时，将显示的用户界面。|
