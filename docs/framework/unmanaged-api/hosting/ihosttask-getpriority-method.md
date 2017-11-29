---
title: "IHostTask::GetPriority 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.GetPriority
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ba32e8c442042f59c8346d68cef7d9f6678ae7dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="d087b-102">IHostTask::GetPriority 方法</span><span class="sxs-lookup"><span data-stu-id="d087b-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="d087b-103">获取表示由当前的任务的线程优先级级别[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="d087b-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d087b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d087b-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d087b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d087b-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="d087b-106">[out]指向一个整数，指示由当前任务的线程优先级级别的`IHostTask`实例。</span><span class="sxs-lookup"><span data-stu-id="d087b-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d087b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d087b-107">Return Value</span></span>  
  
|<span data-ttu-id="d087b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d087b-108">HRESULT</span></span>|<span data-ttu-id="d087b-109">描述</span><span class="sxs-lookup"><span data-stu-id="d087b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d087b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d087b-110">S_OK</span></span>|<span data-ttu-id="d087b-111">`GetPriority`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d087b-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="d087b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d087b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d087b-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d087b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d087b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d087b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d087b-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="d087b-115">The call timed out.</span></span>|  
|<span data-ttu-id="d087b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d087b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d087b-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d087b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d087b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d087b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d087b-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d087b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d087b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d087b-120">E_FAIL</span></span>|<span data-ttu-id="d087b-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d087b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d087b-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="d087b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d087b-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d087b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d087b-124">备注</span><span class="sxs-lookup"><span data-stu-id="d087b-124">Remarks</span></span>  
 <span data-ttu-id="d087b-125">定义由 Win32 线程优先级级别值`SetThreadPriority`函数。</span><span class="sxs-lookup"><span data-stu-id="d087b-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d087b-126">要求</span><span class="sxs-lookup"><span data-stu-id="d087b-126">Requirements</span></span>  
 <span data-ttu-id="d087b-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d087b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d087b-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d087b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d087b-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d087b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d087b-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d087b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d087b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d087b-131">See Also</span></span>  
 [<span data-ttu-id="d087b-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d087b-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d087b-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d087b-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d087b-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d087b-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d087b-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d087b-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
