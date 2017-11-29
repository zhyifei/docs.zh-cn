---
title: "ICLRTask::GetMemStats 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.GetMemStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11537989765d721830c33cb137d1814327b02e14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="d8351-102">ICLRTask::GetMemStats 方法</span><span class="sxs-lookup"><span data-stu-id="d8351-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="d8351-103">获取与任务相关的统计内存使用情况信息的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示。</span><span class="sxs-lookup"><span data-stu-id="d8351-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8351-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8351-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8351-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8351-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="d8351-106">[out]指向的指针[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)实例，其中包含有关的任务，包括分配的字节数的内存使用量的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d8351-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8351-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d8351-107">Return Value</span></span>  
  
|<span data-ttu-id="d8351-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8351-108">HRESULT</span></span>|<span data-ttu-id="d8351-109">描述</span><span class="sxs-lookup"><span data-stu-id="d8351-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8351-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8351-110">S_OK</span></span>|<span data-ttu-id="d8351-111">`GetMemStats`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d8351-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="d8351-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8351-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8351-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d8351-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8351-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8351-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8351-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="d8351-115">The call timed out.</span></span>|  
|<span data-ttu-id="d8351-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8351-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8351-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d8351-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8351-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8351-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8351-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d8351-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8351-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8351-120">E_FAIL</span></span>|<span data-ttu-id="d8351-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d8351-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8351-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="d8351-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8351-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d8351-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8351-124">要求</span><span class="sxs-lookup"><span data-stu-id="d8351-124">Requirements</span></span>  
 <span data-ttu-id="d8351-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8351-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8351-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8351-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8351-127">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d8351-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8351-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8351-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8351-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8351-129">See Also</span></span>  
 [<span data-ttu-id="d8351-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d8351-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d8351-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d8351-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d8351-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d8351-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d8351-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d8351-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
