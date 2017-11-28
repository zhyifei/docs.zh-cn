---
title: "ICLRTask::LocksHeld 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.LocksHeld
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d51fded9f2e475759f2912aea659d272ce08855
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="721bd-102">ICLRTask::LocksHeld 方法</span><span class="sxs-lookup"><span data-stu-id="721bd-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="721bd-103">获取当前在任务上所持有的锁数。</span><span class="sxs-lookup"><span data-stu-id="721bd-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="721bd-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="721bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="721bd-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="721bd-106">[out]在方法调用时，在任务上保留的锁数。</span><span class="sxs-lookup"><span data-stu-id="721bd-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="721bd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="721bd-107">Return Value</span></span>  
  
|<span data-ttu-id="721bd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="721bd-108">HRESULT</span></span>|<span data-ttu-id="721bd-109">描述</span><span class="sxs-lookup"><span data-stu-id="721bd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="721bd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="721bd-110">S_OK</span></span>|<span data-ttu-id="721bd-111">`LocksHeld`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="721bd-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="721bd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="721bd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="721bd-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="721bd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="721bd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="721bd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="721bd-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="721bd-115">The call timed out.</span></span>|  
|<span data-ttu-id="721bd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="721bd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="721bd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="721bd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="721bd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="721bd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="721bd-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="721bd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="721bd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="721bd-120">E_FAIL</span></span>|<span data-ttu-id="721bd-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="721bd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="721bd-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="721bd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="721bd-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="721bd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="721bd-124">要求</span><span class="sxs-lookup"><span data-stu-id="721bd-124">Requirements</span></span>  
 <span data-ttu-id="721bd-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="721bd-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="721bd-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="721bd-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="721bd-127">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="721bd-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="721bd-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="721bd-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721bd-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="721bd-129">See Also</span></span>  
 [<span data-ttu-id="721bd-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="721bd-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="721bd-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="721bd-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="721bd-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="721bd-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="721bd-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="721bd-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
