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
ms.openlocfilehash: 5c7866e0ecc62f037284a5329cb5785be90088f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115838"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="5eb53-102">ICLRMemoryNotificationCallback::OnMemoryNotification 方法</span><span class="sxs-lookup"><span data-stu-id="5eb53-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="5eb53-103">通知公共语言运行时 (CLR) 的计算机上的内存负载。</span><span class="sxs-lookup"><span data-stu-id="5eb53-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb53-104">语法</span><span class="sxs-lookup"><span data-stu-id="5eb53-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eb53-105">参数</span><span class="sxs-lookup"><span data-stu-id="5eb53-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="5eb53-106">[in]之一[EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)值，该值指示内存不足的计算机当前遇到。</span><span class="sxs-lookup"><span data-stu-id="5eb53-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eb53-107">返回值</span><span class="sxs-lookup"><span data-stu-id="5eb53-107">Return Value</span></span>  
  
|<span data-ttu-id="5eb53-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5eb53-108">HRESULT</span></span>|<span data-ttu-id="5eb53-109">描述</span><span class="sxs-lookup"><span data-stu-id="5eb53-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5eb53-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5eb53-110">S_OK</span></span>|`OnMemoryNotification` <span data-ttu-id="5eb53-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5eb53-111">returned successfully.</span></span>|  
|<span data-ttu-id="5eb53-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5eb53-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5eb53-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5eb53-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5eb53-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5eb53-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5eb53-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="5eb53-115">The call timed out.</span></span>|  
|<span data-ttu-id="5eb53-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5eb53-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5eb53-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5eb53-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5eb53-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5eb53-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5eb53-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="5eb53-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5eb53-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5eb53-120">E_FAIL</span></span>|<span data-ttu-id="5eb53-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5eb53-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5eb53-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="5eb53-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5eb53-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5eb53-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eb53-124">备注</span><span class="sxs-lookup"><span data-stu-id="5eb53-124">Remarks</span></span>  
 <span data-ttu-id="5eb53-125">CLR 注册到的回调`OnMemoryNotification`通过使用调用[ihostmemorymanager:: Registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5eb53-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="5eb53-126">运行时使用该回调中返回的信息以在宿主报告资源不足的内存时释放更多的内存。</span><span class="sxs-lookup"><span data-stu-id="5eb53-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5eb53-127">调用`OnMemoryNotification`永远不会阻塞。</span><span class="sxs-lookup"><span data-stu-id="5eb53-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="5eb53-128">它们始终会立即返回。</span><span class="sxs-lookup"><span data-stu-id="5eb53-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eb53-129">要求</span><span class="sxs-lookup"><span data-stu-id="5eb53-129">Requirements</span></span>  
 <span data-ttu-id="5eb53-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb53-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb53-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5eb53-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5eb53-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5eb53-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5eb53-133">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5eb53-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5eb53-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5eb53-134">See also</span></span>

- [<span data-ttu-id="5eb53-135">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="5eb53-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="5eb53-136">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="5eb53-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="5eb53-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="5eb53-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
