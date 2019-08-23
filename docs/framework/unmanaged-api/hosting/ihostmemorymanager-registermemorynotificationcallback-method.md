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
ms.openlocfilehash: 34701642a9e76ec52141e00fe9dde92878faccd2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945438"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="c5b4d-102">IHostMemoryManager::RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="c5b4d-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="c5b4d-103">注册指向主机调用的回调函数的指针, 以便向公共语言运行时 (CLR) 通知当前计算机上的当前内存负载。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5b4d-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5b4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c5b4d-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="c5b4d-106">中一个接口指针, 该指针指向由 CLR 实现的[ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5b4d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c5b4d-107">Return Value</span></span>  
  
|<span data-ttu-id="c5b4d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5b4d-108">HRESULT</span></span>|<span data-ttu-id="c5b4d-109">描述</span><span class="sxs-lookup"><span data-stu-id="c5b4d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5b4d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5b4d-110">S_OK</span></span>|<span data-ttu-id="c5b4d-111">`RegisterMemoryNotificationCallback`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="c5b4d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5b4d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5b4d-113">CLR 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5b4d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5b4d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5b4d-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c5b4d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5b4d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5b4d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5b4d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5b4d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5b4d-119">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5b4d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5b4d-120">E_FAIL</span></span>|<span data-ttu-id="c5b4d-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5b4d-122">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5b4d-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5b4d-124">备注</span><span class="sxs-lookup"><span data-stu-id="c5b4d-124">Remarks</span></span>  
 <span data-ttu-id="c5b4d-125">由于接口仅定义了一个方法 ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) `pCallback` ), 并且是一个指向 CLR 提供的`ICLRMemoryNotificationCallback`实例的指针, 因此注册实际上适用于`ICLRMemoryNotificationCallback`回调函数本身。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="c5b4d-126">宿主调用`OnMemoryNotification`以报告内存压力条件, 而不是使用标准的 Win32 `CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="c5b4d-127">有关详细信息, 请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5b4d-128">对`OnMemoryNotification`从不阻止的的调用。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="c5b4d-129">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b4d-130">要求</span><span class="sxs-lookup"><span data-stu-id="c5b4d-130">Requirements</span></span>  
 <span data-ttu-id="c5b4d-131">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b4d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5b4d-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5b4d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5b4d-133">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c5b4d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5b4d-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b4d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b4d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b4d-135">See also</span></span>

- [<span data-ttu-id="c5b4d-136">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c5b4d-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="c5b4d-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="c5b4d-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
