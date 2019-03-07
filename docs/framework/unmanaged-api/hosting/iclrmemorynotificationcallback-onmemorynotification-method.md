---
title: ICLRMemoryNotificationCallback::OnMemoryNotification 方法
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d395c7eed27893e407b1944523a2f879b56c795d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489301"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="c92fc-102">ICLRMemoryNotificationCallback::OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="c92fc-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="c92fc-103">通知公共语言运行时 (CLR) 的计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="c92fc-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c92fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c92fc-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c92fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="c92fc-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="c92fc-106">[in]之一[EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)值，该值指示内存不足的计算机当前遇到。</span><span class="sxs-lookup"><span data-stu-id="c92fc-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c92fc-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c92fc-107">Return Value</span></span>  
  
|<span data-ttu-id="c92fc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c92fc-108">HRESULT</span></span>|<span data-ttu-id="c92fc-109">描述</span><span class="sxs-lookup"><span data-stu-id="c92fc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c92fc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c92fc-110">S_OK</span></span>|<span data-ttu-id="c92fc-111">`OnMemoryNotification` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c92fc-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="c92fc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c92fc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c92fc-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c92fc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c92fc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c92fc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c92fc-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c92fc-115">The call timed out.</span></span>|  
|<span data-ttu-id="c92fc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c92fc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c92fc-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c92fc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c92fc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c92fc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c92fc-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c92fc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c92fc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c92fc-120">E_FAIL</span></span>|<span data-ttu-id="c92fc-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c92fc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c92fc-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="c92fc-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c92fc-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c92fc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c92fc-124">备注</span><span class="sxs-lookup"><span data-stu-id="c92fc-124">Remarks</span></span>  
 <span data-ttu-id="c92fc-125">CLR 注册到的回调`OnMemoryNotification`通过使用调用[ihostmemorymanager:: Registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c92fc-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="c92fc-126">运行时使用该回调中返回的信息以在宿主报告资源不足的内存时释放更多的内存。</span><span class="sxs-lookup"><span data-stu-id="c92fc-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c92fc-127">调用`OnMemoryNotification`永远不会阻塞。</span><span class="sxs-lookup"><span data-stu-id="c92fc-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="c92fc-128">它们始终会立即返回。</span><span class="sxs-lookup"><span data-stu-id="c92fc-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c92fc-129">要求</span><span class="sxs-lookup"><span data-stu-id="c92fc-129">Requirements</span></span>  
 <span data-ttu-id="c92fc-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c92fc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c92fc-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c92fc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c92fc-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c92fc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c92fc-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c92fc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92fc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c92fc-134">See also</span></span>
- [<span data-ttu-id="c92fc-135">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="c92fc-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="c92fc-136">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="c92fc-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="c92fc-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c92fc-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
