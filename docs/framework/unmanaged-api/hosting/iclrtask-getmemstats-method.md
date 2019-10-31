---
title: ICLRTask::GetMemStats 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
ms.openlocfilehash: 0bf8b6f393806e590be8f97dbfe2d01d5746c339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139706"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="7f7ff-102">ICLRTask::GetMemStats 方法</span><span class="sxs-lookup"><span data-stu-id="7f7ff-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="7f7ff-103">获取与当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示的任务相关的统计内存使用情况信息。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f7ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f7ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f7ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="7f7ff-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="7f7ff-106">弄指向[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)实例的指针，其中包含有关该任务的内存使用情况的详细信息，包括已分配的字节数。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f7ff-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7f7ff-107">Return Value</span></span>  
  
|<span data-ttu-id="7f7ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f7ff-108">HRESULT</span></span>|<span data-ttu-id="7f7ff-109">描述</span><span class="sxs-lookup"><span data-stu-id="7f7ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f7ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f7ff-110">S_OK</span></span>|<span data-ttu-id="7f7ff-111">`GetMemStats` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="7f7ff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f7ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f7ff-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f7ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f7ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f7ff-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="7f7ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f7ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f7ff-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f7ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f7ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f7ff-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f7ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f7ff-120">E_FAIL</span></span>|<span data-ttu-id="7f7ff-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f7ff-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f7ff-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f7ff-124">要求</span><span class="sxs-lookup"><span data-stu-id="7f7ff-124">Requirements</span></span>  
 <span data-ttu-id="7f7ff-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f7ff-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f7ff-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7f7ff-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f7ff-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7f7ff-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f7ff-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f7ff-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f7ff-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f7ff-129">See also</span></span>

- [<span data-ttu-id="7f7ff-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7f7ff-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7f7ff-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7f7ff-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7f7ff-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7f7ff-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7f7ff-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7f7ff-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
