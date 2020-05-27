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
ms.openlocfilehash: ac3a8479cdf05e55885bd55d4e4fb8e6e47686f9
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842393"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="df245-102">IHostTask::SetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="df245-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="df245-103">请求宿主调整当前[IHostTask](ihosttask-interface.md)实例所表示的任务的线程优先级别。</span><span class="sxs-lookup"><span data-stu-id="df245-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df245-104">语法</span><span class="sxs-lookup"><span data-stu-id="df245-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df245-105">参数</span><span class="sxs-lookup"><span data-stu-id="df245-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="df245-106">中一个整数，表示当前实例表示的任务所请求的线程优先级值 `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="df245-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df245-107">返回值</span><span class="sxs-lookup"><span data-stu-id="df245-107">Return Value</span></span>  
  
|<span data-ttu-id="df245-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df245-108">HRESULT</span></span>|<span data-ttu-id="df245-109">说明</span><span class="sxs-lookup"><span data-stu-id="df245-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df245-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="df245-110">S_OK</span></span>|<span data-ttu-id="df245-111">`SetPriority`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="df245-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="df245-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df245-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df245-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="df245-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df245-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df245-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df245-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="df245-115">The call timed out.</span></span>|  
|<span data-ttu-id="df245-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df245-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df245-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="df245-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df245-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df245-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df245-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="df245-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df245-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df245-120">E_FAIL</span></span>|<span data-ttu-id="df245-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="df245-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df245-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="df245-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df245-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="df245-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df245-124">备注</span><span class="sxs-lookup"><span data-stu-id="df245-124">Remarks</span></span>  
 <span data-ttu-id="df245-125">将使用部分基于线程优先级别的轮循机制为线程授予处理时间。</span><span class="sxs-lookup"><span data-stu-id="df245-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="df245-126">`SetPriority`允许 CLR 为当前任务设置该线程优先级别。</span><span class="sxs-lookup"><span data-stu-id="df245-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="df245-127">支持以下 `newPriority` 值。</span><span class="sxs-lookup"><span data-stu-id="df245-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="df245-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="df245-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="df245-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="df245-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="df245-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="df245-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="df245-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="df245-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="df245-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="df245-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="df245-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="df245-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="df245-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="df245-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="df245-135">`SetPriority`当用户代码修改了的值时，CLR 将调用 <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="df245-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="df245-136">宿主可以定义自己的线程优先级分配算法，并可以随意忽略此请求。</span><span class="sxs-lookup"><span data-stu-id="df245-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df245-137">`SetPriority`不会报告线程优先级别是否已更改。</span><span class="sxs-lookup"><span data-stu-id="df245-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="df245-138">调用[IHostTask：： GetPriority](ihosttask-getpriority-method.md)以确定任务的线程优先级别的值。</span><span class="sxs-lookup"><span data-stu-id="df245-138">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="df245-139">线程优先级别值由 Win32 `SetThreadPriority` 函数定义。</span><span class="sxs-lookup"><span data-stu-id="df245-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="df245-140">有关线程优先级的详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="df245-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df245-141">要求</span><span class="sxs-lookup"><span data-stu-id="df245-141">Requirements</span></span>  
 <span data-ttu-id="df245-142">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df245-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df245-143">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="df245-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df245-144">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="df245-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df245-145">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df245-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df245-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df245-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="df245-147">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="df245-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="df245-148">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="df245-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="df245-149">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="df245-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="df245-150">GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="df245-150">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="df245-151">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="df245-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
