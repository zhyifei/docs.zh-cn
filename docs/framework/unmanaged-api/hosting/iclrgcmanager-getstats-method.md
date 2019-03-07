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
ms.openlocfilehash: 3e92707e7b24709d64915e29823196bb0f827175
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485225"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="c6195-102">ICLRGCManager::GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="c6195-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="c6195-103">获取一组有关公共语言运行时的垃圾回收系统的当前统计信息。</span><span class="sxs-lookup"><span data-stu-id="c6195-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6195-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6195-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6195-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6195-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="c6195-106">[in、 out]一个[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)实例，它包含的请求统计信息。</span><span class="sxs-lookup"><span data-stu-id="c6195-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6195-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c6195-107">Return Value</span></span>  
  
|<span data-ttu-id="c6195-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6195-108">HRESULT</span></span>|<span data-ttu-id="c6195-109">描述</span><span class="sxs-lookup"><span data-stu-id="c6195-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6195-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6195-110">S_OK</span></span>|<span data-ttu-id="c6195-111">`GetStats` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c6195-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="c6195-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6195-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6195-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c6195-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6195-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6195-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6195-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c6195-115">The call timed out.</span></span>|  
|<span data-ttu-id="c6195-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6195-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6195-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c6195-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6195-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6195-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6195-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c6195-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6195-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6195-120">E_FAIL</span></span>|<span data-ttu-id="c6195-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c6195-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6195-122">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="c6195-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6195-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c6195-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6195-124">备注</span><span class="sxs-lookup"><span data-stu-id="c6195-124">Remarks</span></span>  
 <span data-ttu-id="c6195-125">CLR 计算并返回由指定这些统计信息`Flags`字段的`pStats`。</span><span class="sxs-lookup"><span data-stu-id="c6195-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="c6195-126">设置`Flags`对一个或多个值的字段[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举来指定在哪些统计信息[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构是设置。</span><span class="sxs-lookup"><span data-stu-id="c6195-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="c6195-127">该用法的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6195-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c6195-128">要求</span><span class="sxs-lookup"><span data-stu-id="c6195-128">Requirements</span></span>  
 <span data-ttu-id="c6195-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6195-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6195-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6195-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6195-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c6195-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6195-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6195-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6195-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6195-133">See also</span></span>
- [<span data-ttu-id="c6195-134">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="c6195-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="c6195-135">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="c6195-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="c6195-136">COR_GC_STAT_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="c6195-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="c6195-137">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="c6195-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="c6195-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="c6195-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c6195-139">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="c6195-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="c6195-140">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="c6195-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="c6195-141">承载接口</span><span class="sxs-lookup"><span data-stu-id="c6195-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c6195-142">承载</span><span class="sxs-lookup"><span data-stu-id="c6195-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
