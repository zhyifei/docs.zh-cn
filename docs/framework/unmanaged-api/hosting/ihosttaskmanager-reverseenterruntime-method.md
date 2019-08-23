---
title: IHostTaskManager::ReverseEnterRuntime 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6e5beabb5ac1b5a4b2a34ae8e18b7fad7c86504
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959055"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="7d529-102">IHostTaskManager::ReverseEnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="7d529-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="7d529-103">通知宿主从非托管代码向公共语言运行时 (CLR) 发出调用。</span><span class="sxs-lookup"><span data-stu-id="7d529-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d529-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d529-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7d529-105">返回值</span><span class="sxs-lookup"><span data-stu-id="7d529-105">Return Value</span></span>  
  
|<span data-ttu-id="7d529-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d529-106">HRESULT</span></span>|<span data-ttu-id="7d529-107">描述</span><span class="sxs-lookup"><span data-stu-id="7d529-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d529-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d529-108">S_OK</span></span>|<span data-ttu-id="7d529-109">`ReverseEnterRuntime`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7d529-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7d529-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d529-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d529-111">CLR 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7d529-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d529-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d529-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d529-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7d529-113">The call timed out.</span></span>|  
|<span data-ttu-id="7d529-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d529-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d529-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7d529-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d529-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d529-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d529-117">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7d529-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d529-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d529-118">E_FAIL</span></span>|<span data-ttu-id="7d529-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7d529-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d529-120">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7d529-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d529-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7d529-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7d529-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7d529-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7d529-123">没有足够的内存可用来完成请求的资源分配。</span><span class="sxs-lookup"><span data-stu-id="7d529-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d529-124">备注</span><span class="sxs-lookup"><span data-stu-id="7d529-124">Remarks</span></span>  
 <span data-ttu-id="7d529-125">如果从托管代码发出的序列发出对 CLR 的调用, 则每次调用`ReverseEnterRuntime`都对应于对[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)的调用。</span><span class="sxs-lookup"><span data-stu-id="7d529-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d529-126">调用可能源自非托管代码, 而不会嵌套。</span><span class="sxs-lookup"><span data-stu-id="7d529-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="7d529-127">在这种情况下, 不会调用[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、或`ReverseLeaveRuntime`, `ReverseEnterRuntime`并且对的调用数不等于对`ReverseLeaveRuntime`的调用次数。</span><span class="sxs-lookup"><span data-stu-id="7d529-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d529-128">要求</span><span class="sxs-lookup"><span data-stu-id="7d529-128">Requirements</span></span>  
 <span data-ttu-id="7d529-129">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d529-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d529-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d529-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d529-131">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7d529-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d529-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d529-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d529-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d529-133">See also</span></span>

- [<span data-ttu-id="7d529-134">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7d529-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7d529-135">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7d529-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7d529-136">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7d529-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7d529-137">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7d529-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
