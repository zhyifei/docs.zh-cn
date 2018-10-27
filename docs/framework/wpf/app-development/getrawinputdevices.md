---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 0cb1184ddc3e8051a68dfed12367dea65a06b623
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50034479"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="61720-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="61720-102">GetRawInputDevices</span></span>
<span data-ttu-id="61720-103">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="61720-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61720-104">语法</span><span class="sxs-lookup"><span data-stu-id="61720-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61720-105">参数</span><span class="sxs-lookup"><span data-stu-id="61720-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="61720-106">[out]一个指向[IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)用于枚举原始输入的设备。</span><span class="sxs-lookup"><span data-stu-id="61720-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="61720-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="61720-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="61720-108">HRESULT：</span><span class="sxs-lookup"><span data-stu-id="61720-108">HRESULT:</span></span>  
  
 <span data-ttu-id="61720-109">S_OK- [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)如果返回 S_OK，则将仅由 PresentationHost.exe 使用。</span><span class="sxs-lookup"><span data-stu-id="61720-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="61720-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="61720-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61720-111">备注</span><span class="sxs-lookup"><span data-stu-id="61720-111">Remarks</span></span>  
 <span data-ttu-id="61720-112">原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。</span><span class="sxs-lookup"><span data-stu-id="61720-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="61720-113">一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。</span><span class="sxs-lookup"><span data-stu-id="61720-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61720-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="61720-114">See Also</span></span>  
 [<span data-ttu-id="61720-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="61720-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)  
 [<span data-ttu-id="61720-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="61720-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
