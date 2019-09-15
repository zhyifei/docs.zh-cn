---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 4fc7a5021f9f8d9e6badcd3e13266fb8f4bfe7a4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991749"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a>参数  
 `ppEnum`  
  
 弄指向用于枚举原始输入设备的[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)的指针。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：  
  
 如果返回 S_OK，则[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)将仅由 presentationhost.exe 使用。  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>备注  
 原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。  
  
 一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。  
  
## <a name="see-also"></a>请参阅

- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](filterinputmessage.md)
