---
title: GetRawInputDevices
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
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5229eb7e72b63f3e44f67dc750d49acbf44410da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
  
 [out]指向的指针[IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)枚举原始输入的设备。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：  
  
 S_OK- [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)将仅由 PresentationHost.exe 如果返回 S_OK。  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>备注  
 原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。  
  
 一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。  
  
## <a name="see-also"></a>请参阅  
 [http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
