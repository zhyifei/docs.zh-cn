---
title: IHostMemoryManager::RegisterMemoryNotificationCallback 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87dfbe85d279aa191253857887c1d9b5b5f8c7cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088517"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="d7984-102">IHostMemoryManager::RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="d7984-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="d7984-103">当前内存负载的计算机上注册的回调函数，宿主通过调用以通知公共语言运行时 (CLR) 的指针。</span><span class="sxs-lookup"><span data-stu-id="d7984-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7984-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7984-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7984-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7984-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="d7984-106">[in]接口指针[ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)由 CLR 实现的实例。</span><span class="sxs-lookup"><span data-stu-id="d7984-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7984-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d7984-107">Return Value</span></span>  
  
|<span data-ttu-id="d7984-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7984-108">HRESULT</span></span>|<span data-ttu-id="d7984-109">描述</span><span class="sxs-lookup"><span data-stu-id="d7984-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7984-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7984-110">S_OK</span></span>|`RegisterMemoryNotificationCallback` <span data-ttu-id="d7984-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d7984-111">returned successfully.</span></span>|  
|<span data-ttu-id="d7984-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7984-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7984-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d7984-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7984-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7984-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7984-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="d7984-115">The call timed out.</span></span>|  
|<span data-ttu-id="d7984-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7984-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7984-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d7984-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7984-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7984-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7984-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d7984-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7984-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7984-120">E_FAIL</span></span>|<span data-ttu-id="d7984-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d7984-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7984-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="d7984-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7984-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d7984-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7984-124">备注</span><span class="sxs-lookup"><span data-stu-id="d7984-124">Remarks</span></span>  
 <span data-ttu-id="d7984-125">因为`ICLRMemoryNotificationCallback`接口定义只有一个方法 ([iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md))，因为`pCallback`是一个指向`ICLRMemoryNotificationCallback`实例提供的 CLR，注册的回调函数本身实际上是。</span><span class="sxs-lookup"><span data-stu-id="d7984-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="d7984-126">宿主通过调用`OnMemoryNotification`到报告内存压力情况，而不使用标准 Win32`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="d7984-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="d7984-127">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="d7984-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7984-128">调用`OnMemoryNotification`永远不会阻塞。</span><span class="sxs-lookup"><span data-stu-id="d7984-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="d7984-129">它们始终会立即返回。</span><span class="sxs-lookup"><span data-stu-id="d7984-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7984-130">要求</span><span class="sxs-lookup"><span data-stu-id="d7984-130">Requirements</span></span>  
 <span data-ttu-id="d7984-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7984-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7984-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7984-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7984-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d7984-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d7984-134">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d7984-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7984-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7984-135">See also</span></span>

- [<span data-ttu-id="d7984-136">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d7984-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="d7984-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="d7984-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
