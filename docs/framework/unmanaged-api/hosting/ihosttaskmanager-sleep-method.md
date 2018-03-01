---
title: "IHostTaskManager::Sleep 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7e51dcd0d5becd0d87850ae542ac437ad651f33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="71b73-102">IHostTaskManager::Sleep 方法</span><span class="sxs-lookup"><span data-stu-id="71b73-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="71b73-103">通知宿主，当前的任务将进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="71b73-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b73-104">语法</span><span class="sxs-lookup"><span data-stu-id="71b73-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71b73-105">参数</span><span class="sxs-lookup"><span data-stu-id="71b73-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="71b73-106">[in]以毫秒为单位，线程将休眠时间间隔。</span><span class="sxs-lookup"><span data-stu-id="71b73-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="71b73-107">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)枚举值，如果此主机应采取的措施，该值指示操作块。</span><span class="sxs-lookup"><span data-stu-id="71b73-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71b73-108">返回值</span><span class="sxs-lookup"><span data-stu-id="71b73-108">Return Value</span></span>  
  
|<span data-ttu-id="71b73-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71b73-109">HRESULT</span></span>|<span data-ttu-id="71b73-110">描述</span><span class="sxs-lookup"><span data-stu-id="71b73-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71b73-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71b73-111">S_OK</span></span>|<span data-ttu-id="71b73-112">`Sleep`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="71b73-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="71b73-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71b73-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71b73-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="71b73-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71b73-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71b73-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71b73-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="71b73-116">The call timed out.</span></span>|  
|<span data-ttu-id="71b73-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71b73-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71b73-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="71b73-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71b73-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71b73-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71b73-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="71b73-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71b73-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71b73-121">E_FAIL</span></span>|<span data-ttu-id="71b73-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="71b73-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71b73-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="71b73-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71b73-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="71b73-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71b73-125">备注</span><span class="sxs-lookup"><span data-stu-id="71b73-125">Remarks</span></span>  
 <span data-ttu-id="71b73-126">CLR 通常调用`IHostTaskManager::Sleep`时<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>从用户代码调用。</span><span class="sxs-lookup"><span data-stu-id="71b73-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71b73-127">惠?</span><span class="sxs-lookup"><span data-stu-id="71b73-127">Requirements</span></span>  
 <span data-ttu-id="71b73-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71b73-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b73-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71b73-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71b73-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71b73-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71b73-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b73-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b73-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="71b73-132">See Also</span></span>  
 [<span data-ttu-id="71b73-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="71b73-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="71b73-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="71b73-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="71b73-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="71b73-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="71b73-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="71b73-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
