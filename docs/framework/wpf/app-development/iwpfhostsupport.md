---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423650"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
通过 Presentationhost.exe 承载 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 内容的应用程序实现此接口，以提供主机与 Presentationhost.exe 之间的集成点。  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 的应用程序（如 Web 浏览器）可以承载 WPF 内容，包括 XAML 浏览器应用程序（Xbap）和松散 XAML。 若要承载 WPF 内容，[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 应用程序创建[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)的实例。 若要承载，WPF 将创建 Presentationhost.exe 的一个实例，该实例向宿主提供承载的 WPF 内容以显示在[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)中。  
  
 `IWpfHostSupport` 启用的集成允许 Presentationhost.exe 执行以下操作：  
  
- 发现并注册到主机应用程序感兴趣的原始输入设备（人机接口设备）。  
  
- 从已注册的原始输入设备接收输入消息，并将相应的消息转发到主机应用程序。  
  
- 查询主机应用程序以获取自定义进度和错误用户界面。  
  
> [!NOTE]
> 此 API 预期仅支持在本地客户端计算机上使用  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。|  
|[FilterInputMessage](filterinputmessage.md)|除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。|  
|[GetCustomUI](getcustomui.md)|默认情况下，Presentationhost.exe 提供其自己的部署进度以及部署 WPF 内容时显示的部署错误用户界面。|
