---
title: IHostTaskManager::ReverseLeaveRuntime 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9f5b6ad4765edfdea9f56debad085d69e9fc769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680434"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="0d7c0-102">IHostTaskManager::ReverseLeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="0d7c0-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="0d7c0-103">通知主机控制正在离开公共语言运行时 (CLR) 并输入从托管代码调用非托管的函数。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d7c0-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0d7c0-105">返回值</span><span class="sxs-lookup"><span data-stu-id="0d7c0-105">Return Value</span></span>  
  
|<span data-ttu-id="0d7c0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d7c0-106">HRESULT</span></span>|<span data-ttu-id="0d7c0-107">描述</span><span class="sxs-lookup"><span data-stu-id="0d7c0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d7c0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d7c0-108">S_OK</span></span>|<span data-ttu-id="0d7c0-109">`ReverseLeaveRuntime` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="0d7c0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d7c0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d7c0-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d7c0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d7c0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d7c0-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-113">The call timed out.</span></span>|  
|<span data-ttu-id="0d7c0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d7c0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d7c0-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d7c0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d7c0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d7c0-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d7c0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d7c0-118">E_FAIL</span></span>|<span data-ttu-id="0d7c0-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d7c0-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d7c0-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0d7c0-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0d7c0-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0d7c0-123">没有足够的内存是可用于完成请求的资源分配。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d7c0-124">备注</span><span class="sxs-lookup"><span data-stu-id="0d7c0-124">Remarks</span></span>  
 <span data-ttu-id="0d7c0-125">CLR 调用`ReverseLeaveRuntime`来通知返回当前执行的任务宿主控件从托管代码通过平台调用非托管函数调用。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="0d7c0-126">每次调用`ReverseLeaveRuntime`匹配相应地调用[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7c0-127">要求</span><span class="sxs-lookup"><span data-stu-id="0d7c0-127">Requirements</span></span>  
 <span data-ttu-id="0d7c0-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d7c0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d7c0-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d7c0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d7c0-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0d7c0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d7c0-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7c0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7c0-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d7c0-132">See also</span></span>
- [<span data-ttu-id="0d7c0-133">CallNeedsHostHook 方法</span><span class="sxs-lookup"><span data-stu-id="0d7c0-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="0d7c0-134">EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="0d7c0-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="0d7c0-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="0d7c0-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0d7c0-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="0d7c0-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0d7c0-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="0d7c0-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0d7c0-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="0d7c0-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="0d7c0-139">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="0d7c0-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- [<span data-ttu-id="0d7c0-140">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="0d7c0-140">A Closer Look at Platform Invoke</span></span>](https://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)
