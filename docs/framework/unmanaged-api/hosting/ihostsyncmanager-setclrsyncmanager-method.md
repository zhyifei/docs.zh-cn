---
title: "IHostSyncManager::SetCLRSyncManager 方法"
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
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fca59f0d2617c6fb244b2b1ed7b5cf46a7d5869f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="95ebd-102">IHostSyncManager::SetCLRSyncManager 方法</span><span class="sxs-lookup"><span data-stu-id="95ebd-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="95ebd-103">集[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例要与当前关联[IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="95ebd-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ebd-104">语法</span><span class="sxs-lookup"><span data-stu-id="95ebd-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95ebd-105">参数</span><span class="sxs-lookup"><span data-stu-id="95ebd-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="95ebd-106">[in]指向的指针`ICLRSyncManager`由公共语言运行时 (CLR) 提供的实例。</span><span class="sxs-lookup"><span data-stu-id="95ebd-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95ebd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="95ebd-107">Return Value</span></span>  
  
|<span data-ttu-id="95ebd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95ebd-108">HRESULT</span></span>|<span data-ttu-id="95ebd-109">描述</span><span class="sxs-lookup"><span data-stu-id="95ebd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95ebd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95ebd-110">S_OK</span></span>|<span data-ttu-id="95ebd-111">`SetCLRSyncManager`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="95ebd-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="95ebd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95ebd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95ebd-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="95ebd-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95ebd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95ebd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95ebd-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="95ebd-115">The call timed out.</span></span>|  
|<span data-ttu-id="95ebd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95ebd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95ebd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="95ebd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95ebd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95ebd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95ebd-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="95ebd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95ebd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95ebd-120">E_FAIL</span></span>|<span data-ttu-id="95ebd-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="95ebd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95ebd-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="95ebd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95ebd-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="95ebd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95ebd-124">备注</span><span class="sxs-lookup"><span data-stu-id="95ebd-124">Remarks</span></span>  
 <span data-ttu-id="95ebd-125">为了便于主机与 CLR 之间的通信，承载接口通常成对出现。</span><span class="sxs-lookup"><span data-stu-id="95ebd-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="95ebd-126">由宿主，实现对的一个成员和由 CLR 实现其他成员。</span><span class="sxs-lookup"><span data-stu-id="95ebd-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="95ebd-127">作为主机端实现，`IHostSyncManager`接口对应于`ICLRSyncManager`由 CLR 实现接口。</span><span class="sxs-lookup"><span data-stu-id="95ebd-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="95ebd-128">CLR 调用`SetCLRSyncManager`提供`ICLRSyncManager`主机将与当前相关联的实例`IHostSyncManager`实例。</span><span class="sxs-lookup"><span data-stu-id="95ebd-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95ebd-129">惠?</span><span class="sxs-lookup"><span data-stu-id="95ebd-129">Requirements</span></span>  
 <span data-ttu-id="95ebd-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95ebd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95ebd-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95ebd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95ebd-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="95ebd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95ebd-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95ebd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ebd-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="95ebd-134">See Also</span></span>  
 [<span data-ttu-id="95ebd-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="95ebd-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="95ebd-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="95ebd-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
