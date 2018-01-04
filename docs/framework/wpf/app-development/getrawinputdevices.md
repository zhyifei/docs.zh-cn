---
title: GetRawInputDevices
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5229eb7e72b63f3e44f67dc750d49acbf44410da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getrawinputdevices"></a><span data-ttu-id="3d0cd-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="3d0cd-102">GetRawInputDevices</span></span>
<span data-ttu-id="3d0cd-103">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="3d0cd-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d0cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d0cd-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d0cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="3d0cd-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="3d0cd-106">[out]指向的指针[IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)枚举原始输入的设备。</span><span class="sxs-lookup"><span data-stu-id="3d0cd-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3d0cd-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="3d0cd-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="3d0cd-108">HRESULT：</span><span class="sxs-lookup"><span data-stu-id="3d0cd-108">HRESULT:</span></span>  
  
 <span data-ttu-id="3d0cd-109">S_OK- [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)将仅由 PresentationHost.exe 如果返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="3d0cd-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="3d0cd-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3d0cd-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d0cd-111">备注</span><span class="sxs-lookup"><span data-stu-id="3d0cd-111">Remarks</span></span>  
 <span data-ttu-id="3d0cd-112">原始输入设备是一组输入设备，其中包括键盘、鼠标和非传统设备（如远程控制设备）。</span><span class="sxs-lookup"><span data-stu-id="3d0cd-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="3d0cd-113">一旦已检索到的原始输入设备的列表，则 PresentationHost.exe 将使用此设备进行注册，以接收 WM_INPUT 通知消息。</span><span class="sxs-lookup"><span data-stu-id="3d0cd-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d0cd-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d0cd-114">See Also</span></span>  
 [<span data-ttu-id="3d0cd-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span><span class="sxs-lookup"><span data-stu-id="3d0cd-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [<span data-ttu-id="3d0cd-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="3d0cd-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
