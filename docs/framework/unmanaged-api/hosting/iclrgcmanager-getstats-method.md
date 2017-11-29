---
title: "ICLRGCManager::GetStats 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06d52bd0348e4667f1e3ec43a371021922f12ded
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="05a09-102">ICLRGCManager::GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="05a09-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="05a09-103">获取一组有关公共语言运行时的垃圾回收系统的当前统计信息。</span><span class="sxs-lookup"><span data-stu-id="05a09-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05a09-104">语法</span><span class="sxs-lookup"><span data-stu-id="05a09-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05a09-105">参数</span><span class="sxs-lookup"><span data-stu-id="05a09-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="05a09-106">[在中，out]A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)实例，其中包含请求的统计信息。</span><span class="sxs-lookup"><span data-stu-id="05a09-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05a09-107">返回值</span><span class="sxs-lookup"><span data-stu-id="05a09-107">Return Value</span></span>  
  
|<span data-ttu-id="05a09-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05a09-108">HRESULT</span></span>|<span data-ttu-id="05a09-109">描述</span><span class="sxs-lookup"><span data-stu-id="05a09-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05a09-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="05a09-110">S_OK</span></span>|<span data-ttu-id="05a09-111">`GetStats`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="05a09-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="05a09-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="05a09-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="05a09-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="05a09-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="05a09-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="05a09-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="05a09-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="05a09-115">The call timed out.</span></span>|  
|<span data-ttu-id="05a09-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="05a09-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="05a09-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="05a09-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="05a09-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="05a09-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="05a09-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="05a09-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="05a09-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="05a09-120">E_FAIL</span></span>|<span data-ttu-id="05a09-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="05a09-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="05a09-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="05a09-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="05a09-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="05a09-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05a09-124">备注</span><span class="sxs-lookup"><span data-stu-id="05a09-124">Remarks</span></span>  
 <span data-ttu-id="05a09-125">CLR 计算并返回由指定这些统计信息`Flags`字段`pStats`。</span><span class="sxs-lookup"><span data-stu-id="05a09-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="05a09-126">设置`Flags`为一个或多个值的字段[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举来指定在哪些统计信息[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构不是设置。</span><span class="sxs-lookup"><span data-stu-id="05a09-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="05a09-127">使用情况的一个示例是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="05a09-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="05a09-128">要求</span><span class="sxs-lookup"><span data-stu-id="05a09-128">Requirements</span></span>  
 <span data-ttu-id="05a09-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05a09-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05a09-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05a09-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05a09-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="05a09-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05a09-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05a09-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a09-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05a09-133">See Also</span></span>  
 [<span data-ttu-id="05a09-134">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="05a09-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="05a09-135">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="05a09-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="05a09-136">COR_GC_STAT_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="05a09-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [<span data-ttu-id="05a09-137">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="05a09-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="05a09-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="05a09-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="05a09-139">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="05a09-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="05a09-140">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="05a09-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="05a09-141">承载接口</span><span class="sxs-lookup"><span data-stu-id="05a09-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="05a09-142">承载</span><span class="sxs-lookup"><span data-stu-id="05a09-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
