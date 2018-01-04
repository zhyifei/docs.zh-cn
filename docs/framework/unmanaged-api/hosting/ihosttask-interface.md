---
title: "IHostTask 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask
helpviewer_keywords: IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbffe2a171c112d4e9650b2c1b2a9ce1f010f382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttask-interface"></a><span data-ttu-id="4d8ad-102">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="4d8ad-102">IHostTask Interface</span></span>
<span data-ttu-id="4d8ad-103">提供允许公共语言运行时 (CLR) 与要管理任务的主机进行通信的方法。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d8ad-104">方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-104">Methods</span></span>  
  
|<span data-ttu-id="4d8ad-105">方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-105">Method</span></span>|<span data-ttu-id="4d8ad-106">描述</span><span class="sxs-lookup"><span data-stu-id="4d8ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d8ad-107">Alert 方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="4d8ad-108">主机唤醒表示由当前的任务的请求`IHostTask`实例，因此可以中止该任务。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="4d8ad-109">GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="4d8ad-110">获取表示由当前的任务的线程优先级级别`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="4d8ad-111">Join 方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="4d8ad-112">阻止调用的任务，直到表示由当前的任务`IHostTask`实例完成后，在指定的时间间隔结束，或[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="4d8ad-113">SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="4d8ad-114">将相关联[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)与当前实例`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="4d8ad-115">SetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="4d8ad-116">表示由当前的任务的请求主机调整的线程优先级级别`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="4d8ad-117">Start 方法</span><span class="sxs-lookup"><span data-stu-id="4d8ad-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="4d8ad-118">主机将表示由当前的任务的请求`IHostTask`实例从挂起状态与代码可以执行的实时状态。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d8ad-119">备注</span><span class="sxs-lookup"><span data-stu-id="4d8ad-119">Remarks</span></span>  
 <span data-ttu-id="4d8ad-120">CLR 调用由定义方法`IHostTask`启动任务，来设置其线程优先级级别，依次类推。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d8ad-121">惠?</span><span class="sxs-lookup"><span data-stu-id="4d8ad-121">Requirements</span></span>  
 <span data-ttu-id="4d8ad-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d8ad-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d8ad-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d8ad-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d8ad-124">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4d8ad-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d8ad-125">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d8ad-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8ad-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d8ad-126">See Also</span></span>  
 [<span data-ttu-id="4d8ad-127">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="4d8ad-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="4d8ad-128">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="4d8ad-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4d8ad-129">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="4d8ad-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="4d8ad-130">承载接口</span><span class="sxs-lookup"><span data-stu-id="4d8ad-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
