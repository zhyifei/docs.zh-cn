---
title: IHostTaskManager 接口
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da30e75bf4a58e66bb0dd8210368b162cf14c3f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936469"
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="c2206-102">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c2206-102">IHostTaskManager Interface</span></span>
<span data-ttu-id="c2206-103">提供允许公共语言运行时 (CLR) 用于通过而不是使用标准操作系统线程或纤程函数主机的任务的方法。</span><span class="sxs-lookup"><span data-stu-id="c2206-103">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2206-104">方法</span><span class="sxs-lookup"><span data-stu-id="c2206-104">Methods</span></span>  
  
|<span data-ttu-id="c2206-105">方法</span><span class="sxs-lookup"><span data-stu-id="c2206-105">Method</span></span>|<span data-ttu-id="c2206-106">描述</span><span class="sxs-lookup"><span data-stu-id="c2206-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2206-107">BeginDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-107">BeginDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="c2206-108">通知宿主托管代码进入不能在其中中止当前任务的周期。</span><span class="sxs-lookup"><span data-stu-id="c2206-108">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="c2206-109">BeginThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-109">BeginThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="c2206-110">通知宿主托管代码进入在其中将当前的任务必须不移动到另一个操作系统线程的周期。</span><span class="sxs-lookup"><span data-stu-id="c2206-110">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="c2206-111">CallNeedsHostHook 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-111">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="c2206-112">使宿主能够指定公共语言运行时是否可以内联指定调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="c2206-112">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="c2206-113">CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-113">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|<span data-ttu-id="c2206-114">主机创建新的任务的请求。</span><span class="sxs-lookup"><span data-stu-id="c2206-114">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="c2206-115">EndDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-115">EndDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="c2206-116">通知宿主托管代码正在退出在其中不必须中止当前任务，周期遵循早期调用`BeginDelayAbort`。</span><span class="sxs-lookup"><span data-stu-id="c2206-116">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="c2206-117">EndThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-117">EndThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="c2206-118">通知宿主托管代码正在退出不能在其当前任务移动到另一个操作系统线程，周期遵循早期调用`BeginThreadAffinity`。</span><span class="sxs-lookup"><span data-stu-id="c2206-118">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="c2206-119">EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-119">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="c2206-120">通知主机，对非托管方法的调用以便为平台调用方法，将执行控制返回到 CLR。</span><span class="sxs-lookup"><span data-stu-id="c2206-120">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="c2206-121">GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-121">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="c2206-122">获取从其进行此调用的操作系统线程当前正在执行的任务的接口指针。</span><span class="sxs-lookup"><span data-stu-id="c2206-122">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="c2206-123">GetStackGuarantee 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-123">GetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="c2206-124">获取的堆栈空间后的堆栈操作完成后，可保证，但在关闭进程之前的量。</span><span class="sxs-lookup"><span data-stu-id="c2206-124">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="c2206-125">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-125">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="c2206-126">通知宿主托管代码将要对非托管函数进行调用。</span><span class="sxs-lookup"><span data-stu-id="c2206-126">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="c2206-127">ReverseEnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-127">ReverseEnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="c2206-128">通知主机正在到公共语言运行时 (CLR) 从非托管代码进行调用。</span><span class="sxs-lookup"><span data-stu-id="c2206-128">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="c2206-129">ReverseLeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-129">ReverseLeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="c2206-130">通知主机控制正在离开 CLR 并输入从托管代码调用非托管的函数。</span><span class="sxs-lookup"><span data-stu-id="c2206-130">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="c2206-131">SetCLRTaskManager 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-131">SetCLRTaskManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="c2206-132">为宿主提供的接口指针到[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)由 CLR 实现的实例。</span><span class="sxs-lookup"><span data-stu-id="c2206-132">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="c2206-133">SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-133">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="c2206-134">通知宿主 CLR 已更改了当前任务中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="c2206-134">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="c2206-135">SetStackGuarantee 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-135">SetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="c2206-136">保留以仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="c2206-136">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="c2206-137">SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-137">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="c2206-138">通知主机用户界面区域设置已在当前任务。</span><span class="sxs-lookup"><span data-stu-id="c2206-138">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="c2206-139">Sleep 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-139">Sleep Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|<span data-ttu-id="c2206-140">通知主机当前任务即将进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="c2206-140">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="c2206-141">SwitchToTask 方法</span><span class="sxs-lookup"><span data-stu-id="c2206-141">SwitchToTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="c2206-142">通知主机应切换当前任务。</span><span class="sxs-lookup"><span data-stu-id="c2206-142">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2206-143">备注</span><span class="sxs-lookup"><span data-stu-id="c2206-143">Remarks</span></span>  
 <span data-ttu-id="c2206-144">`IHostTaskManager` 使 CLR 能够创建和管理任务，以提供挂钩，以便主机控件从托管代码转换到非托管代码，反之亦然时, 执行的操作并指定特定的操作，主机可以并且不能创建在代码执行过程。</span><span class="sxs-lookup"><span data-stu-id="c2206-144">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2206-145">要求</span><span class="sxs-lookup"><span data-stu-id="c2206-145">Requirements</span></span>  
 <span data-ttu-id="c2206-146">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2206-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2206-147">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2206-147">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2206-148">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2206-148">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2206-149">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2206-149">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2206-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2206-150">See also</span></span>

- [<span data-ttu-id="c2206-151">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="c2206-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c2206-152">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c2206-152">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c2206-153">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="c2206-153">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c2206-154">承载接口</span><span class="sxs-lookup"><span data-stu-id="c2206-154">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
