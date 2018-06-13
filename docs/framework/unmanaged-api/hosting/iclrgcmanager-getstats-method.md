---
title: ICLRGCManager::GetStats 方法
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96673049d37034781dff9f206db86a1d5d953d52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436395"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="6f380-102">ICLRGCManager::GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="6f380-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="6f380-103">获取一组有关公共语言运行时的垃圾回收系统的当前统计信息。</span><span class="sxs-lookup"><span data-stu-id="6f380-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f380-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f380-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f380-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f380-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="6f380-106">[在中，out]A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)实例，其中包含请求的统计信息。</span><span class="sxs-lookup"><span data-stu-id="6f380-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f380-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6f380-107">Return Value</span></span>  
  
|<span data-ttu-id="6f380-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f380-108">HRESULT</span></span>|<span data-ttu-id="6f380-109">描述</span><span class="sxs-lookup"><span data-stu-id="6f380-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f380-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f380-110">S_OK</span></span>|<span data-ttu-id="6f380-111">`GetStats` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6f380-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="6f380-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f380-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f380-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6f380-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f380-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f380-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f380-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="6f380-115">The call timed out.</span></span>|  
|<span data-ttu-id="6f380-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f380-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f380-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6f380-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f380-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f380-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f380-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="6f380-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f380-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f380-120">E_FAIL</span></span>|<span data-ttu-id="6f380-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6f380-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f380-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="6f380-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f380-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6f380-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f380-124">备注</span><span class="sxs-lookup"><span data-stu-id="6f380-124">Remarks</span></span>  
 <span data-ttu-id="6f380-125">CLR 计算并返回由指定这些统计信息`Flags`字段`pStats`。</span><span class="sxs-lookup"><span data-stu-id="6f380-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="6f380-126">设置`Flags`为一个或多个值的字段[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举来指定在哪些统计信息[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构不是设置。</span><span class="sxs-lookup"><span data-stu-id="6f380-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="6f380-127">使用情况的一个示例是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f380-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="6f380-128">要求</span><span class="sxs-lookup"><span data-stu-id="6f380-128">Requirements</span></span>  
 <span data-ttu-id="6f380-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f380-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f380-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f380-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f380-131">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6f380-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f380-132">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f380-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f380-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f380-133">See Also</span></span>  
 [<span data-ttu-id="6f380-134">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="6f380-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="6f380-135">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="6f380-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="6f380-136">COR_GC_STAT_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="6f380-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [<span data-ttu-id="6f380-137">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="6f380-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="6f380-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="6f380-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="6f380-139">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="6f380-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="6f380-140">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="6f380-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="6f380-141">承载接口</span><span class="sxs-lookup"><span data-stu-id="6f380-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6f380-142">承载</span><span class="sxs-lookup"><span data-stu-id="6f380-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
