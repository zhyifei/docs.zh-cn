---
title: IHostTask 接口
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: f8f476f681764a46700dd5ec83c8f9b2739f18f6
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842476"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="e8418-102">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="e8418-102">IHostTask Interface</span></span>
<span data-ttu-id="e8418-103">提供允许公共语言运行时（CLR）与宿主通信以管理任务的方法。</span><span class="sxs-lookup"><span data-stu-id="e8418-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8418-104">方法</span><span class="sxs-lookup"><span data-stu-id="e8418-104">Methods</span></span>  
  
|<span data-ttu-id="e8418-105">方法</span><span class="sxs-lookup"><span data-stu-id="e8418-105">Method</span></span>|<span data-ttu-id="e8418-106">说明</span><span class="sxs-lookup"><span data-stu-id="e8418-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8418-107">Alert 方法</span><span class="sxs-lookup"><span data-stu-id="e8418-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="e8418-108">请求宿主唤醒当前实例表示的任务 `IHostTask` ，以便可以中止任务。</span><span class="sxs-lookup"><span data-stu-id="e8418-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="e8418-109">GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="e8418-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="e8418-110">获取当前实例表示的任务的线程优先级别 `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="e8418-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e8418-111">Join 方法</span><span class="sxs-lookup"><span data-stu-id="e8418-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="e8418-112">阻止调用任务，直到当前实例表示的任务 `IHostTask` 完成、指定的时间间隔结束或调用[IHostTask：： Alert](ihosttask-alert-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="e8418-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="e8418-113">SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="e8418-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="e8418-114">将[ICLRTask 接口](iclrtask-interface.md)实例与当前实例相关联 `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="e8418-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e8418-115">SetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="e8418-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="e8418-116">请求宿主调整当前实例所表示的任务的线程优先级别 `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="e8418-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e8418-117">Start 方法</span><span class="sxs-lookup"><span data-stu-id="e8418-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="e8418-118">请求宿主将当前实例表示的任务 `IHostTask` 从挂起状态移动到实时状态，在此状态下可以执行代码。</span><span class="sxs-lookup"><span data-stu-id="e8418-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8418-119">备注</span><span class="sxs-lookup"><span data-stu-id="e8418-119">Remarks</span></span>  
 <span data-ttu-id="e8418-120">CLR 调用定义的方法 `IHostTask` 来启动任务、设置其线程优先级别，等等。</span><span class="sxs-lookup"><span data-stu-id="e8418-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8418-121">要求</span><span class="sxs-lookup"><span data-stu-id="e8418-121">Requirements</span></span>  
 <span data-ttu-id="e8418-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8418-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8418-123">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e8418-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8418-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e8418-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8418-125">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8418-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8418-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8418-126">See also</span></span>

- [<span data-ttu-id="e8418-127">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="e8418-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e8418-128">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e8418-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e8418-129">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e8418-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="e8418-130">承载接口</span><span class="sxs-lookup"><span data-stu-id="e8418-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
