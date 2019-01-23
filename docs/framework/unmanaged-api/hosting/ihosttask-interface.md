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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d862c02e96487049fb88f80665d32caf6939ed1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555930"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="e25c3-102">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="e25c3-102">IHostTask Interface</span></span>
<span data-ttu-id="e25c3-103">提供允许公共语言运行时 (CLR) 与要管理任务的主机进行通信的方法。</span><span class="sxs-lookup"><span data-stu-id="e25c3-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e25c3-104">方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-104">Methods</span></span>  
  
|<span data-ttu-id="e25c3-105">方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-105">Method</span></span>|<span data-ttu-id="e25c3-106">描述</span><span class="sxs-lookup"><span data-stu-id="e25c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e25c3-107">Alert 方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="e25c3-108">请求主机唤醒表示由当前的任务`IHostTask`的实例，因此，任务可以中止。</span><span class="sxs-lookup"><span data-stu-id="e25c3-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="e25c3-109">GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="e25c3-110">获取表示当前的任务的线程优先级别`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="e25c3-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e25c3-111">Join 方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="e25c3-112">阻止，直到表示由当前的任务调用任务`IHostTask`实例完成后，指定的时间间隔结束，或[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="e25c3-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="e25c3-113">SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="e25c3-114">将相关联[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)与当前实例`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="e25c3-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e25c3-115">SetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="e25c3-116">请求主机调整线程优先级级别表示由当前的任务`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="e25c3-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e25c3-117">Start 方法</span><span class="sxs-lookup"><span data-stu-id="e25c3-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="e25c3-118">请求主机将由当前的任务`IHostTask`实例从挂起状态到实时状态，可以在其中执行代码。</span><span class="sxs-lookup"><span data-stu-id="e25c3-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e25c3-119">备注</span><span class="sxs-lookup"><span data-stu-id="e25c3-119">Remarks</span></span>  
 <span data-ttu-id="e25c3-120">CLR 调用由定义的方法`IHostTask`启动任务，来设置其线程优先级级别，依次类推。</span><span class="sxs-lookup"><span data-stu-id="e25c3-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e25c3-121">要求</span><span class="sxs-lookup"><span data-stu-id="e25c3-121">Requirements</span></span>  
 <span data-ttu-id="e25c3-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e25c3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e25c3-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e25c3-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e25c3-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e25c3-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e25c3-125">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e25c3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25c3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e25c3-126">See also</span></span>
- [<span data-ttu-id="e25c3-127">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="e25c3-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e25c3-128">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e25c3-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e25c3-129">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e25c3-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e25c3-130">承载接口</span><span class="sxs-lookup"><span data-stu-id="e25c3-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
