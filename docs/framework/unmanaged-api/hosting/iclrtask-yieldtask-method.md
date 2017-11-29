---
title: "ICLRTask::YieldTask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.YieldTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a02a69329958593aec546ca9c60e3d201ce2a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="77a27-102">ICLRTask::YieldTask 方法</span><span class="sxs-lookup"><span data-stu-id="77a27-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="77a27-103">请求公共语言运行时 (CLR) 将留出放任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示，并将的处理器时间提供给其他任务。</span><span class="sxs-lookup"><span data-stu-id="77a27-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a27-104">语法</span><span class="sxs-lookup"><span data-stu-id="77a27-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="77a27-105">返回值</span><span class="sxs-lookup"><span data-stu-id="77a27-105">Return Value</span></span>  
  
|<span data-ttu-id="77a27-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77a27-106">HRESULT</span></span>|<span data-ttu-id="77a27-107">描述</span><span class="sxs-lookup"><span data-stu-id="77a27-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77a27-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="77a27-108">S_OK</span></span>|<span data-ttu-id="77a27-109">`YieldTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="77a27-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="77a27-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77a27-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77a27-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="77a27-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77a27-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77a27-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77a27-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="77a27-113">The call timed out.</span></span>|  
|<span data-ttu-id="77a27-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77a27-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77a27-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="77a27-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77a27-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77a27-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77a27-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="77a27-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77a27-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77a27-118">E_FAIL</span></span>|<span data-ttu-id="77a27-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="77a27-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77a27-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="77a27-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77a27-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="77a27-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77a27-122">备注</span><span class="sxs-lookup"><span data-stu-id="77a27-122">Remarks</span></span>  
 <span data-ttu-id="77a27-123">主机可调用`YieldTask`对请求对其他任务或进程的处理器资源。</span><span class="sxs-lookup"><span data-stu-id="77a27-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="77a27-124">此方法主要是为了允许长时间运行的代码会放弃 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="77a27-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="77a27-125">在运行时尝试将此任务放置，当前`ICLRTask`实例表示在其中可以生成处理时间，但不能保证是否成功的状态。</span><span class="sxs-lookup"><span data-stu-id="77a27-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a27-126">要求</span><span class="sxs-lookup"><span data-stu-id="77a27-126">Requirements</span></span>  
 <span data-ttu-id="77a27-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77a27-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a27-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77a27-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77a27-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77a27-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77a27-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a27-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a27-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77a27-131">See Also</span></span>  
 [<span data-ttu-id="77a27-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="77a27-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="77a27-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="77a27-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="77a27-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="77a27-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="77a27-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="77a27-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
