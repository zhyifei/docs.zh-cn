---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 3531ff9f42289a3ad3b029f090f2dd4987e5886c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199399"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a>参数  
 `ppEnum`  
  
 [out]一个指向[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)用于枚举原始输入的设备。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：  
  
 S_OK- [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)如果返回 S_OK，则将仅由 PresentationHost.exe 使用。  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>备注  
 原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。  
  
 一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。  
  
## <a name="see-also"></a>请参阅

- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](filterinputmessage.md)
