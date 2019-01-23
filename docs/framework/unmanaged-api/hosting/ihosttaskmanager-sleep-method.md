---
title: IHostTaskManager::Sleep 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9661d1cd6994acf2c622350593ede502929f3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510645"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="92727-102">IHostTaskManager::Sleep 方法</span><span class="sxs-lookup"><span data-stu-id="92727-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="92727-103">通知主机当前任务即将进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="92727-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92727-104">语法</span><span class="sxs-lookup"><span data-stu-id="92727-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92727-105">参数</span><span class="sxs-lookup"><span data-stu-id="92727-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="92727-106">[in]时间间隔，以毫秒为单位，线程将休眠。</span><span class="sxs-lookup"><span data-stu-id="92727-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="92727-107">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)枚举值，如果此主机应采取什么操作，该值指示操作块。</span><span class="sxs-lookup"><span data-stu-id="92727-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92727-108">返回值</span><span class="sxs-lookup"><span data-stu-id="92727-108">Return Value</span></span>  
  
|<span data-ttu-id="92727-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92727-109">HRESULT</span></span>|<span data-ttu-id="92727-110">描述</span><span class="sxs-lookup"><span data-stu-id="92727-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92727-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="92727-111">S_OK</span></span>|<span data-ttu-id="92727-112">`Sleep` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="92727-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="92727-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="92727-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="92727-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="92727-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="92727-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="92727-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="92727-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="92727-116">The call timed out.</span></span>|  
|<span data-ttu-id="92727-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="92727-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="92727-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="92727-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="92727-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="92727-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="92727-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="92727-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="92727-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92727-121">E_FAIL</span></span>|<span data-ttu-id="92727-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="92727-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="92727-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="92727-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="92727-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="92727-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92727-125">备注</span><span class="sxs-lookup"><span data-stu-id="92727-125">Remarks</span></span>  
 <span data-ttu-id="92727-126">CLR 通常会调用`IHostTaskManager::Sleep`时<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>从用户代码调用。</span><span class="sxs-lookup"><span data-stu-id="92727-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92727-127">要求</span><span class="sxs-lookup"><span data-stu-id="92727-127">Requirements</span></span>  
 <span data-ttu-id="92727-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92727-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92727-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="92727-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92727-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="92727-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92727-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92727-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92727-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="92727-132">See also</span></span>
- [<span data-ttu-id="92727-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="92727-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="92727-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="92727-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="92727-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="92727-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="92727-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="92727-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
