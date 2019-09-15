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
# <a name="getrawinputdevices"></a><span data-ttu-id="b0b5a-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="b0b5a-102">GetRawInputDevices</span></span>
<span data-ttu-id="b0b5a-103">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="b0b5a-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0b5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0b5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0b5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0b5a-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="b0b5a-106">弄指向用于枚举原始输入设备的[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)的指针。</span><span class="sxs-lookup"><span data-stu-id="b0b5a-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b0b5a-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="b0b5a-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="b0b5a-108">HRESULT：</span><span class="sxs-lookup"><span data-stu-id="b0b5a-108">HRESULT:</span></span>  
  
 <span data-ttu-id="b0b5a-109">如果返回 S_OK，则[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)将仅由 presentationhost.exe 使用。</span><span class="sxs-lookup"><span data-stu-id="b0b5a-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="b0b5a-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b0b5a-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0b5a-111">备注</span><span class="sxs-lookup"><span data-stu-id="b0b5a-111">Remarks</span></span>  
 <span data-ttu-id="b0b5a-112">原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。</span><span class="sxs-lookup"><span data-stu-id="b0b5a-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="b0b5a-113">一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。</span><span class="sxs-lookup"><span data-stu-id="b0b5a-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b5a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0b5a-114">See also</span></span>

- [<span data-ttu-id="b0b5a-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="b0b5a-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="b0b5a-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="b0b5a-116">FilterInputMessage</span></span>](filterinputmessage.md)
