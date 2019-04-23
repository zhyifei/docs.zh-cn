---
title: ICLRTask::YieldTask 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc8d936ac4fca704e7e3069209d8ff75d46b044d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113667"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="146c6-102">ICLRTask::YieldTask 方法</span><span class="sxs-lookup"><span data-stu-id="146c6-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="146c6-103">请求公共语言运行时 (CLR) 到某个位置放置该任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例所表示，并使处理器时间可供其他任务。</span><span class="sxs-lookup"><span data-stu-id="146c6-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="146c6-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="146c6-105">返回值</span><span class="sxs-lookup"><span data-stu-id="146c6-105">Return Value</span></span>  
  
|<span data-ttu-id="146c6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="146c6-106">HRESULT</span></span>|<span data-ttu-id="146c6-107">描述</span><span class="sxs-lookup"><span data-stu-id="146c6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="146c6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="146c6-108">S_OK</span></span>|<span data-ttu-id="146c6-109">`YieldTask` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="146c6-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="146c6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="146c6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="146c6-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="146c6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="146c6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="146c6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="146c6-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="146c6-113">The call timed out.</span></span>|  
|<span data-ttu-id="146c6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="146c6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="146c6-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="146c6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="146c6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="146c6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="146c6-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="146c6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="146c6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="146c6-118">E_FAIL</span></span>|<span data-ttu-id="146c6-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="146c6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="146c6-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="146c6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="146c6-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="146c6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="146c6-122">备注</span><span class="sxs-lookup"><span data-stu-id="146c6-122">Remarks</span></span>  
 <span data-ttu-id="146c6-123">主机调用`YieldTask`请求的其他任务或进程的处理器资源。</span><span class="sxs-lookup"><span data-stu-id="146c6-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="146c6-124">此方法主要是为了允许运行时间较长代码放弃 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="146c6-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="146c6-125">在运行时尝试将此任务放置的当前`ICLRTask`实例表示在其中它可以产生处理时间，但是不能保证成功的状态。</span><span class="sxs-lookup"><span data-stu-id="146c6-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146c6-126">要求</span><span class="sxs-lookup"><span data-stu-id="146c6-126">Requirements</span></span>  
 <span data-ttu-id="146c6-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="146c6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146c6-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="146c6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="146c6-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="146c6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="146c6-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="146c6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146c6-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="146c6-131">See also</span></span>

- [<span data-ttu-id="146c6-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="146c6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="146c6-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="146c6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="146c6-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="146c6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="146c6-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="146c6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
