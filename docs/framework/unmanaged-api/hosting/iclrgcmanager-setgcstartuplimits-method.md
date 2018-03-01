---
title: "ICLRGCManager::SetGCStartupLimits 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fd5a1135866b75ea1d11fc5a14289104edfeac4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="07ec6-102">ICLRGCManager::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="07ec6-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="07ec6-103">设置的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小。</span><span class="sxs-lookup"><span data-stu-id="07ec6-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07ec6-104">从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、 可以设置段大小和最大第 0 代大小值大于`DWORD`使用[iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="07ec6-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ec6-105">语法</span><span class="sxs-lookup"><span data-stu-id="07ec6-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07ec6-106">参数</span><span class="sxs-lookup"><span data-stu-id="07ec6-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="07ec6-107">[in]垃圾回收段指定的大小。</span><span class="sxs-lookup"><span data-stu-id="07ec6-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="07ec6-108">最小的段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="07ec6-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="07ec6-109">段可以增加增量为 1 MB 或更大。</span><span class="sxs-lookup"><span data-stu-id="07ec6-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="07ec6-110">[in]第 0 代指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="07ec6-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="07ec6-111">最小的第 0 代大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="07ec6-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07ec6-112">返回值</span><span class="sxs-lookup"><span data-stu-id="07ec6-112">Return Value</span></span>  
  
|<span data-ttu-id="07ec6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07ec6-113">HRESULT</span></span>|<span data-ttu-id="07ec6-114">描述</span><span class="sxs-lookup"><span data-stu-id="07ec6-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07ec6-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="07ec6-115">S_OK</span></span>|<span data-ttu-id="07ec6-116">`SetGCStartupLimits`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="07ec6-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="07ec6-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="07ec6-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="07ec6-118">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="07ec6-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="07ec6-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="07ec6-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="07ec6-120">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="07ec6-120">The call timed out.</span></span>|  
|<span data-ttu-id="07ec6-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="07ec6-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="07ec6-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="07ec6-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="07ec6-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="07ec6-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="07ec6-124">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="07ec6-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="07ec6-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="07ec6-125">E_FAIL</span></span>|<span data-ttu-id="07ec6-126">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="07ec6-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="07ec6-127">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="07ec6-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="07ec6-128">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="07ec6-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07ec6-129">备注</span><span class="sxs-lookup"><span data-stu-id="07ec6-129">Remarks</span></span>  
 <span data-ttu-id="07ec6-130">值的`SetGCStartupLimits`集可以只能指定一次。</span><span class="sxs-lookup"><span data-stu-id="07ec6-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="07ec6-131">更高版本调用`SetGCStartupLimits`将被忽略。</span><span class="sxs-lookup"><span data-stu-id="07ec6-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ec6-132">惠?</span><span class="sxs-lookup"><span data-stu-id="07ec6-132">Requirements</span></span>  
 <span data-ttu-id="07ec6-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07ec6-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07ec6-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="07ec6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07ec6-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="07ec6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07ec6-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ec6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ec6-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="07ec6-137">See Also</span></span>  
 [<span data-ttu-id="07ec6-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="07ec6-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="07ec6-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="07ec6-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="07ec6-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="07ec6-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="07ec6-141">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="07ec6-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
