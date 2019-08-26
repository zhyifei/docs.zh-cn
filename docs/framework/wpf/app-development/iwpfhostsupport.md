---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964780"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
通过 presentationhost.exe 托管[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]内容的应用程序实现此接口, 以在主机和 presentationhost.exe 之间提供集成点。  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]诸如 Web 浏览器之类的应用[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]程序可以承载[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]内容, 包括和松散 XAML。 若要[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]承载内容[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] , 应用程序将创建[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)的实例。 若要托管, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]将创建 presentationhost.exe 的实例, 该实例向宿主提供承载[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]的内容, 以便在[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)中显示。  
  
 启用的集成`IWpfHostSupport`允许 presentationhost.exe 执行以下操作:  
  
- 发现并注册到主机应用程序感兴趣的原始输入设备 (人机接口设备)。  
  
- 从已注册的原始输入设备接收输入消息, 并将相应的消息转发到主机应用程序。  
  
- 查询主机应用程序以获取自定义进度和错误用户界面。  
  
> [!NOTE]
> 此 API 预期仅支持在本地客户端计算机上使用  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。|  
|[FilterInputMessage](filterinputmessage.md)|除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。|  
|[GetCustomUI](getcustomui.md)|默认情况下, Presentationhost.exe 提供其自己的部署进度以及部署 WPF 内容时显示的部署错误用户界面。|
