---
title: IHostTask::SetPriority 方法
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9335cb182355931b31040f164c9e51a67598f7b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748033"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="9995c-102">IHostTask::SetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="9995c-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="9995c-103">请求主机调整线程优先级级别表示由当前的任务[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="9995c-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9995c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9995c-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9995c-105">参数</span><span class="sxs-lookup"><span data-stu-id="9995c-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="9995c-106">[in]一个整数，表示由当前任务的请求的线程优先级值`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="9995c-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9995c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9995c-107">Return Value</span></span>  
  
|<span data-ttu-id="9995c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9995c-108">HRESULT</span></span>|<span data-ttu-id="9995c-109">描述</span><span class="sxs-lookup"><span data-stu-id="9995c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9995c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9995c-110">S_OK</span></span>|<span data-ttu-id="9995c-111">`SetPriority` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9995c-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="9995c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9995c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9995c-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9995c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9995c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9995c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9995c-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="9995c-115">The call timed out.</span></span>|  
|<span data-ttu-id="9995c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9995c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9995c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9995c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9995c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9995c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9995c-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="9995c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9995c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9995c-120">E_FAIL</span></span>|<span data-ttu-id="9995c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9995c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9995c-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="9995c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9995c-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9995c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9995c-124">备注</span><span class="sxs-lookup"><span data-stu-id="9995c-124">Remarks</span></span>  
 <span data-ttu-id="9995c-125">线程授予处理使用部分基于线程的优先级级别的轮循机制系统的时间。</span><span class="sxs-lookup"><span data-stu-id="9995c-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="9995c-126">`SetPriority` 使 CLR 能够设置当前任务的线程优先级别。</span><span class="sxs-lookup"><span data-stu-id="9995c-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="9995c-127">以下`newPriority`支持值。</span><span class="sxs-lookup"><span data-stu-id="9995c-127">The following `newPriority` values are supported.</span></span>  
  
-   <span data-ttu-id="9995c-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="9995c-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
-   <span data-ttu-id="9995c-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="9995c-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
-   <span data-ttu-id="9995c-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="9995c-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
-   <span data-ttu-id="9995c-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="9995c-131">THREAD_PRIORITY_IDLE</span></span>  
  
-   <span data-ttu-id="9995c-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="9995c-132">THREAD_PRIORITY_LOWEST</span></span>  
  
-   <span data-ttu-id="9995c-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="9995c-133">THREAD_PRIORITY_NORMAL</span></span>  
  
-   <span data-ttu-id="9995c-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="9995c-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="9995c-135">CLR 调用`SetPriority`时的值<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>修改由用户代码。</span><span class="sxs-lookup"><span data-stu-id="9995c-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="9995c-136">主机可以定义其自己的线程优先级分配算法，并且可以自由地忽略此请求。</span><span class="sxs-lookup"><span data-stu-id="9995c-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9995c-137">`SetPriority` 不报告线程优先级别是否已更改。</span><span class="sxs-lookup"><span data-stu-id="9995c-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="9995c-138">调用[ihosttask:: Getpriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)来确定任务的线程优先级别的值。</span><span class="sxs-lookup"><span data-stu-id="9995c-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="9995c-139">线程优先级别值定义由 Win32`SetThreadPriority`函数。</span><span class="sxs-lookup"><span data-stu-id="9995c-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="9995c-140">有关线程优先级的详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="9995c-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9995c-141">要求</span><span class="sxs-lookup"><span data-stu-id="9995c-141">Requirements</span></span>  
 <span data-ttu-id="9995c-142">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9995c-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9995c-143">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9995c-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9995c-144">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9995c-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9995c-145">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9995c-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9995c-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="9995c-146">See also</span></span>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="9995c-147">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9995c-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9995c-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9995c-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9995c-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="9995c-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9995c-150">GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="9995c-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="9995c-151">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9995c-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
