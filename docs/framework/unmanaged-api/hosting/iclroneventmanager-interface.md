---
title: ICLROnEventManager 接口
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182996"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="937be-102">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="937be-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="937be-103">提供允许主机以注册和注销公共语言运行时 (CLR) 事件的回调方法。</span><span class="sxs-lookup"><span data-stu-id="937be-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="937be-104">方法</span><span class="sxs-lookup"><span data-stu-id="937be-104">Methods</span></span>  
  
|<span data-ttu-id="937be-105">方法</span><span class="sxs-lookup"><span data-stu-id="937be-105">Method</span></span>|<span data-ttu-id="937be-106">描述</span><span class="sxs-lookup"><span data-stu-id="937be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="937be-107">RegisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="937be-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="937be-108">注册指定的事件的回调指针。</span><span class="sxs-lookup"><span data-stu-id="937be-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="937be-109">UnregisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="937be-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="937be-110">注销以前注册的回调指针为指定的事件。</span><span class="sxs-lookup"><span data-stu-id="937be-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="937be-111">备注</span><span class="sxs-lookup"><span data-stu-id="937be-111">Remarks</span></span>  
 <span data-ttu-id="937be-112">若要注册和注销事件的回调，主机获取的引用`ICLROnEventManager`通过调用[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="937be-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="937be-113">所描述的事件[EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)不止一次和来自不同线程发出信号卸载或禁用 CLR 可以激发。</span><span class="sxs-lookup"><span data-stu-id="937be-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="937be-114">要求</span><span class="sxs-lookup"><span data-stu-id="937be-114">Requirements</span></span>  
 <span data-ttu-id="937be-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="937be-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="937be-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="937be-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="937be-117">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="937be-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="937be-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="937be-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="937be-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="937be-119">See also</span></span>

- [<span data-ttu-id="937be-120">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="937be-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="937be-121">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="937be-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="937be-122">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="937be-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="937be-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="937be-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
