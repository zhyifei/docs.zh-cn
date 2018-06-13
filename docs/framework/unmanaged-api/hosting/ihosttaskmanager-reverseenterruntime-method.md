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
ms.openlocfilehash: e0945a4b32a155e99e0402dfcdcc826d1eff3eb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442015"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="bd7cb-102">IHostTaskManager::ReverseEnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="bd7cb-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="bd7cb-103">通知主机正在到公共语言运行时 (CLR) 从非托管代码进行调用。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd7cb-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bd7cb-105">返回值</span><span class="sxs-lookup"><span data-stu-id="bd7cb-105">Return Value</span></span>  
  
|<span data-ttu-id="bd7cb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd7cb-106">HRESULT</span></span>|<span data-ttu-id="bd7cb-107">描述</span><span class="sxs-lookup"><span data-stu-id="bd7cb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd7cb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd7cb-108">S_OK</span></span>|<span data-ttu-id="bd7cb-109">`ReverseEnterRuntime` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="bd7cb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd7cb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd7cb-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd7cb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd7cb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd7cb-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-113">The call timed out.</span></span>|  
|<span data-ttu-id="bd7cb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd7cb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd7cb-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd7cb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd7cb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd7cb-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd7cb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd7cb-118">E_FAIL</span></span>|<span data-ttu-id="bd7cb-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd7cb-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd7cb-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bd7cb-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bd7cb-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bd7cb-123">没有足够的内存是可用于完成请求的资源分配。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd7cb-124">备注</span><span class="sxs-lookup"><span data-stu-id="bd7cb-124">Remarks</span></span>  
 <span data-ttu-id="bd7cb-125">如果从产生的序列进行到 CLR 调用时在托管代码中，则每个调用`ReverseEnterRuntime`对应于调用[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd7cb-126">调用中，可来自而无需嵌套的非托管代码。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="bd7cb-127">在这种情况下，没有不需要调用[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)， [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)，或`ReverseLeaveRuntime`，和对的调用数`ReverseEnterRuntime`不等于对的调用数`ReverseLeaveRuntime`。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd7cb-128">要求</span><span class="sxs-lookup"><span data-stu-id="bd7cb-128">Requirements</span></span>  
 <span data-ttu-id="bd7cb-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd7cb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd7cb-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd7cb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd7cb-131">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bd7cb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd7cb-132">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd7cb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7cb-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd7cb-133">See Also</span></span>  
 [<span data-ttu-id="bd7cb-134">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="bd7cb-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="bd7cb-135">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="bd7cb-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="bd7cb-136">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="bd7cb-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="bd7cb-137">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="bd7cb-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
