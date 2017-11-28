---
title: "ICLROnEventManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager
helpviewer_keywords: ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3f792af3e01d476768961928272cb6166a144f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="5b152-102">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="5b152-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="5b152-103">提供允许主机注册和取消注册为公共语言运行时 (CLR) 事件的回调的方法。</span><span class="sxs-lookup"><span data-stu-id="5b152-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b152-104">方法</span><span class="sxs-lookup"><span data-stu-id="5b152-104">Methods</span></span>  
  
|<span data-ttu-id="5b152-105">方法</span><span class="sxs-lookup"><span data-stu-id="5b152-105">Method</span></span>|<span data-ttu-id="5b152-106">描述</span><span class="sxs-lookup"><span data-stu-id="5b152-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b152-107">RegisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="5b152-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="5b152-108">注册指定的事件的回调指针。</span><span class="sxs-lookup"><span data-stu-id="5b152-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="5b152-109">UnregisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="5b152-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="5b152-110">注销之前注册的回调指针为指定的事件。</span><span class="sxs-lookup"><span data-stu-id="5b152-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b152-111">备注</span><span class="sxs-lookup"><span data-stu-id="5b152-111">Remarks</span></span>  
 <span data-ttu-id="5b152-112">若要注册和注销事件回调，主机获取的引用`ICLROnEventManager`通过调用[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5b152-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b152-113">通过所述的事件[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)不止一次和从不同的线程以指示卸载或禁用 CLR 可以激发。</span><span class="sxs-lookup"><span data-stu-id="5b152-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b152-114">要求</span><span class="sxs-lookup"><span data-stu-id="5b152-114">Requirements</span></span>  
 <span data-ttu-id="5b152-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b152-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b152-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b152-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b152-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5b152-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b152-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b152-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b152-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b152-119">See Also</span></span>  
 [<span data-ttu-id="5b152-120">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="5b152-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="5b152-121">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="5b152-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="5b152-122">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="5b152-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="5b152-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="5b152-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
