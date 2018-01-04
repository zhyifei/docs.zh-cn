---
title: "IHostTaskManager::ReverseLeaveRuntime 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseLeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa16e640cade9304916650c4ea13231cacb967f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="8d7c2-102">IHostTaskManager::ReverseLeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="8d7c2-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="8d7c2-103">通知主机控制正在离开公共语言运行时 (CLR) 并输入从托管代码调用非托管的函数。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d7c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d7c2-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8d7c2-105">返回值</span><span class="sxs-lookup"><span data-stu-id="8d7c2-105">Return Value</span></span>  
  
|<span data-ttu-id="8d7c2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d7c2-106">HRESULT</span></span>|<span data-ttu-id="8d7c2-107">描述</span><span class="sxs-lookup"><span data-stu-id="8d7c2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d7c2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d7c2-108">S_OK</span></span>|<span data-ttu-id="8d7c2-109">`ReverseLeaveRuntime`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="8d7c2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d7c2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d7c2-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d7c2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d7c2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d7c2-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-113">The call timed out.</span></span>|  
|<span data-ttu-id="8d7c2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d7c2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d7c2-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d7c2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d7c2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d7c2-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d7c2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d7c2-118">E_FAIL</span></span>|<span data-ttu-id="8d7c2-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d7c2-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d7c2-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8d7c2-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8d7c2-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8d7c2-123">没有足够的内存是可用于完成请求的资源分配。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d7c2-124">备注</span><span class="sxs-lookup"><span data-stu-id="8d7c2-124">Remarks</span></span>  
 <span data-ttu-id="8d7c2-125">CLR 调用`ReverseLeaveRuntime`来通知返回当前正在执行的任务宿主控件添加到从通过平台的托管代码调用非托管函数调用。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="8d7c2-126">每次调用`ReverseLeaveRuntime`匹配相应地调用[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d7c2-127">惠?</span><span class="sxs-lookup"><span data-stu-id="8d7c2-127">Requirements</span></span>  
 <span data-ttu-id="8d7c2-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7c2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d7c2-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d7c2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d7c2-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8d7c2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d7c2-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d7c2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d7c2-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d7c2-132">See Also</span></span>  
 [<span data-ttu-id="8d7c2-133">CallNeedsHostHook 方法</span><span class="sxs-lookup"><span data-stu-id="8d7c2-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)  
 [<span data-ttu-id="8d7c2-134">EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="8d7c2-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)  
 [<span data-ttu-id="8d7c2-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="8d7c2-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8d7c2-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8d7c2-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8d7c2-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="8d7c2-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8d7c2-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8d7c2-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="8d7c2-139">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="8d7c2-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)  
 [<span data-ttu-id="8d7c2-140">详述平台调用</span><span class="sxs-lookup"><span data-stu-id="8d7c2-140">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)
