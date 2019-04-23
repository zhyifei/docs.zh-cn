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
# <a name="getrawinputdevices"></a><span data-ttu-id="d11f6-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="d11f6-102">GetRawInputDevices</span></span>
<span data-ttu-id="d11f6-103">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="d11f6-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="d11f6-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d11f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="d11f6-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="d11f6-106">[out]一个指向[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)用于枚举原始输入的设备。</span><span class="sxs-lookup"><span data-stu-id="d11f6-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d11f6-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d11f6-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="d11f6-108">HRESULT：</span><span class="sxs-lookup"><span data-stu-id="d11f6-108">HRESULT:</span></span>  
  
 <span data-ttu-id="d11f6-109">S_OK- [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)如果返回 S_OK，则将仅由 PresentationHost.exe 使用。</span><span class="sxs-lookup"><span data-stu-id="d11f6-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="d11f6-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d11f6-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d11f6-111">备注</span><span class="sxs-lookup"><span data-stu-id="d11f6-111">Remarks</span></span>  
 <span data-ttu-id="d11f6-112">原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。</span><span class="sxs-lookup"><span data-stu-id="d11f6-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="d11f6-113">一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。</span><span class="sxs-lookup"><span data-stu-id="d11f6-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11f6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d11f6-114">See also</span></span>

- [<span data-ttu-id="d11f6-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="d11f6-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="d11f6-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="d11f6-116">FilterInputMessage</span></span>](filterinputmessage.md)
