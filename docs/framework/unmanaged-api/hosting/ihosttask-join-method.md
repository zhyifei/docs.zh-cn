---
title: "IHostTask::Join 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Join
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b5dbfcfc87a520925f36e09d4f2d21dbffadfe1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="040ba-102">IHostTask::Join 方法</span><span class="sxs-lookup"><span data-stu-id="040ba-102">IHostTask::Join Method</span></span>
<span data-ttu-id="040ba-103">阻止调用的任务，直到表示由当前的任务[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例完成后，在指定的时间间隔结束，或[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="040ba-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="040ba-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="040ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="040ba-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="040ba-106">[in]时间间隔，以毫秒为单位，以等待任务终止。</span><span class="sxs-lookup"><span data-stu-id="040ba-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="040ba-107">如果此时间间隔过后任务终止之前，将取消阻止调用的任务。</span><span class="sxs-lookup"><span data-stu-id="040ba-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="040ba-108">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="040ba-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="040ba-109">值为 WAIT_ALERTABLE 指示如果唤醒任务宿主`Alert`之前调用`milliseconds`间隔。</span><span class="sxs-lookup"><span data-stu-id="040ba-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="040ba-110">返回值</span><span class="sxs-lookup"><span data-stu-id="040ba-110">Return Value</span></span>  
  
|<span data-ttu-id="040ba-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="040ba-111">HRESULT</span></span>|<span data-ttu-id="040ba-112">描述</span><span class="sxs-lookup"><span data-stu-id="040ba-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="040ba-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="040ba-113">S_OK</span></span>|<span data-ttu-id="040ba-114">`Join`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="040ba-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="040ba-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="040ba-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="040ba-116">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="040ba-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="040ba-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="040ba-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="040ba-118">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="040ba-118">The call timed out.</span></span>|  
|<span data-ttu-id="040ba-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="040ba-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="040ba-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="040ba-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="040ba-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="040ba-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="040ba-122">事件已取消时被阻塞的线程或纤程正在等待它，或者当前`IHostTask`实例不是与任务关联。</span><span class="sxs-lookup"><span data-stu-id="040ba-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="040ba-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="040ba-123">E_FAIL</span></span>|<span data-ttu-id="040ba-124">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="040ba-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="040ba-125">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="040ba-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="040ba-126">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="040ba-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="040ba-127">要求</span><span class="sxs-lookup"><span data-stu-id="040ba-127">Requirements</span></span>  
 <span data-ttu-id="040ba-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="040ba-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="040ba-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="040ba-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="040ba-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="040ba-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="040ba-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="040ba-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040ba-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="040ba-132">See Also</span></span>  
 [<span data-ttu-id="040ba-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="040ba-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="040ba-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="040ba-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="040ba-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="040ba-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="040ba-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="040ba-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="040ba-137">WAIT_OPTION 枚举</span><span class="sxs-lookup"><span data-stu-id="040ba-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
