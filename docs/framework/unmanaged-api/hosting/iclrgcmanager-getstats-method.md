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
ms.openlocfilehash: 9e8b65c735028029f4fb44c2640df74ef171d9de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141139"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="5818b-102">ICLRGCManager::GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="5818b-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="5818b-103">获取有关公共语言运行时的垃圾回收系统的当前统计信息集。</span><span class="sxs-lookup"><span data-stu-id="5818b-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5818b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5818b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5818b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5818b-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="5818b-106">[in，out]包含请求的统计信息的[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)实例。</span><span class="sxs-lookup"><span data-stu-id="5818b-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5818b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="5818b-107">Return Value</span></span>  
  
|<span data-ttu-id="5818b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5818b-108">HRESULT</span></span>|<span data-ttu-id="5818b-109">描述</span><span class="sxs-lookup"><span data-stu-id="5818b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5818b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5818b-110">S_OK</span></span>|<span data-ttu-id="5818b-111">`GetStats` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="5818b-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="5818b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5818b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5818b-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5818b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5818b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5818b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5818b-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="5818b-115">The call timed out.</span></span>|  
|<span data-ttu-id="5818b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5818b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5818b-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5818b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5818b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5818b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5818b-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="5818b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5818b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5818b-120">E_FAIL</span></span>|<span data-ttu-id="5818b-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5818b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5818b-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="5818b-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5818b-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5818b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5818b-124">备注</span><span class="sxs-lookup"><span data-stu-id="5818b-124">Remarks</span></span>  
 <span data-ttu-id="5818b-125">CLR 只计算并返回由 `pStats`的 `Flags` 字段指定的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5818b-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="5818b-126">将 `Flags` 字段设置为一个或多个[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)枚举值，以指定要设置[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构中的哪些统计信息。</span><span class="sxs-lookup"><span data-stu-id="5818b-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="5818b-127">用法的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="5818b-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5818b-128">要求</span><span class="sxs-lookup"><span data-stu-id="5818b-128">Requirements</span></span>  
 <span data-ttu-id="5818b-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5818b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5818b-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5818b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5818b-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5818b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5818b-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5818b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5818b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5818b-133">See also</span></span>

- [<span data-ttu-id="5818b-134">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="5818b-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5818b-135">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="5818b-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="5818b-136">COR_GC_STAT_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="5818b-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="5818b-137">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="5818b-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5818b-138">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="5818b-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5818b-139">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="5818b-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="5818b-140">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="5818b-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="5818b-141">承载接口</span><span class="sxs-lookup"><span data-stu-id="5818b-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5818b-142">承载</span><span class="sxs-lookup"><span data-stu-id="5818b-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
