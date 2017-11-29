---
title: FilterInputMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b3a0e58c7485d46f004db7ea52215be60340b68
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="filterinputmessage"></a>FilterInputMessage
除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>参数  
 `pMsg`  
  
 [in] 发送给正在获得原始输入的窗口的 WM_INPUT 消息。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：  
  
 S_OK - 筛选器未处理该消息，且可能执行进一步处理。  
  
 S_FALSE - 筛选器已处理此消息，且应执行进一步处理。  
  
 E_NOTIMPL – 如果返回此值， [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)不会再次调用。 这可能会从以下主机应用程序返回：仅对向 PresentationHost.exe 提供自定义进度和错误用户界面有兴趣且对从 PresentationHost.exe 向自身转发原始输入消息不感兴趣。  
  
## <a name="remarks"></a>备注  
 PresentationHost.exe 是各种原始输入设备（包括键盘、鼠标和远程控件）的目标。 有时，主机应用程序中的行为取决于输入，否则将由 PresentationHost.exe 消耗。 例如，主机应用程序可能依靠接收特定输入消息来确定是否显示特定的用户界面元素。  
  
 若要允许主机应用程序以接收必要的输入的消息以提供这些行为，PresentationHost.exe 相应原始输入将消息转发到托管的应用程序通过调用[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)。  
  
 托管应用程序收到原始输入的消息通过注册与原始输入设备 （人机接口设备） 返回的套[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)。  
  
## <a name="see-also"></a>另请参阅  
 [WM_INPUT 通知](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
