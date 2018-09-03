---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 1611183dc02e46ea6d5fbb53c26500be3ed93d0d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483945"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
  
 [out]一个指向[IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)用于枚举原始输入的设备。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：  
  
 S_OK- [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)如果返回 S_OK，则将仅由 PresentationHost.exe 使用。  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>备注  
 原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。  
  
 一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。  
  
## <a name="see-also"></a>请参阅  
 [http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
