---
title: "IHostTask::SetPriority 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.SetPriority
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34dabcb35f46d4a2b0536e00fa1fd69637b14cb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="95f2c-102">IHostTask::SetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="95f2c-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="95f2c-103">表示由当前的任务的请求主机调整的线程优先级级别[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="95f2c-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f2c-104">语法</span><span class="sxs-lookup"><span data-stu-id="95f2c-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95f2c-105">参数</span><span class="sxs-lookup"><span data-stu-id="95f2c-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="95f2c-106">[in]一个整数，表示由当前的任务的请求的线程优先级值`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="95f2c-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95f2c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="95f2c-107">Return Value</span></span>  
  
|<span data-ttu-id="95f2c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95f2c-108">HRESULT</span></span>|<span data-ttu-id="95f2c-109">描述</span><span class="sxs-lookup"><span data-stu-id="95f2c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95f2c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95f2c-110">S_OK</span></span>|<span data-ttu-id="95f2c-111">`SetPriority`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="95f2c-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="95f2c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95f2c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95f2c-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="95f2c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95f2c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95f2c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95f2c-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="95f2c-115">The call timed out.</span></span>|  
|<span data-ttu-id="95f2c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95f2c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95f2c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="95f2c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95f2c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95f2c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95f2c-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="95f2c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95f2c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95f2c-120">E_FAIL</span></span>|<span data-ttu-id="95f2c-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="95f2c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95f2c-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="95f2c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95f2c-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="95f2c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95f2c-124">备注</span><span class="sxs-lookup"><span data-stu-id="95f2c-124">Remarks</span></span>  
 <span data-ttu-id="95f2c-125">线程授予处理使用部分基于线程的优先级级别的轮循机制系统的时间。</span><span class="sxs-lookup"><span data-stu-id="95f2c-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="95f2c-126">`SetPriority`允许设置为当前的任务的线程优先级级别的 CLR。</span><span class="sxs-lookup"><span data-stu-id="95f2c-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="95f2c-127">以下`newPriority`支持值。</span><span class="sxs-lookup"><span data-stu-id="95f2c-127">The following `newPriority` values are supported.</span></span>  
  
-   <span data-ttu-id="95f2c-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="95f2c-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
-   <span data-ttu-id="95f2c-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="95f2c-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
-   <span data-ttu-id="95f2c-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="95f2c-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
-   <span data-ttu-id="95f2c-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="95f2c-131">THREAD_PRIORITY_IDLE</span></span>  
  
-   <span data-ttu-id="95f2c-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="95f2c-132">THREAD_PRIORITY_LOWEST</span></span>  
  
-   <span data-ttu-id="95f2c-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="95f2c-133">THREAD_PRIORITY_NORMAL</span></span>  
  
-   <span data-ttu-id="95f2c-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="95f2c-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="95f2c-135">CLR 调用`SetPriority`时的值<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>已由用户代码修改。</span><span class="sxs-lookup"><span data-stu-id="95f2c-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="95f2c-136">主机可以定义自己的线程优先级分配算法，并且可以自由地忽略此请求。</span><span class="sxs-lookup"><span data-stu-id="95f2c-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95f2c-137">`SetPriority`不会报告是否进行了更改的线程优先级别。</span><span class="sxs-lookup"><span data-stu-id="95f2c-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="95f2c-138">调用[ihosttask:: Getpriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)以确定该任务的线程优先级级别的值。</span><span class="sxs-lookup"><span data-stu-id="95f2c-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="95f2c-139">定义由 Win32 线程优先级级别值`SetThreadPriority`函数。</span><span class="sxs-lookup"><span data-stu-id="95f2c-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="95f2c-140">有关线程优先级的详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="95f2c-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f2c-141">要求</span><span class="sxs-lookup"><span data-stu-id="95f2c-141">Requirements</span></span>  
 <span data-ttu-id="95f2c-142">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95f2c-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f2c-143">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95f2c-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95f2c-144">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="95f2c-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95f2c-145">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f2c-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f2c-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95f2c-146">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="95f2c-147">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="95f2c-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="95f2c-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="95f2c-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="95f2c-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="95f2c-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="95f2c-150">GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="95f2c-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)  
 [<span data-ttu-id="95f2c-151">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="95f2c-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
