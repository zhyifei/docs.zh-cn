---
title: IHostTaskManager::BeginThreadAffinity 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67a133604e269b8c20dc8640b91e378c498cf038
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745568"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="37ded-102">IHostTaskManager::BeginThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="37ded-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="37ded-103">通知宿主托管代码进入在其中将当前的任务必须不移动到另一个操作系统线程的周期。</span><span class="sxs-lookup"><span data-stu-id="37ded-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ded-104">语法</span><span class="sxs-lookup"><span data-stu-id="37ded-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="37ded-105">返回值</span><span class="sxs-lookup"><span data-stu-id="37ded-105">Return Value</span></span>  
  
|<span data-ttu-id="37ded-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37ded-106">HRESULT</span></span>|<span data-ttu-id="37ded-107">描述</span><span class="sxs-lookup"><span data-stu-id="37ded-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37ded-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="37ded-108">S_OK</span></span>|<span data-ttu-id="37ded-109">`BeginThreadAffinity` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="37ded-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="37ded-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37ded-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37ded-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="37ded-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37ded-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37ded-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37ded-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="37ded-113">The call timed out.</span></span>|  
|<span data-ttu-id="37ded-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37ded-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37ded-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="37ded-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37ded-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37ded-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37ded-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="37ded-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37ded-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37ded-118">E_FAIL</span></span>|<span data-ttu-id="37ded-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="37ded-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37ded-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="37ded-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37ded-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="37ded-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37ded-122">备注</span><span class="sxs-lookup"><span data-stu-id="37ded-122">Remarks</span></span>  
 <span data-ttu-id="37ded-123">CLR 通常会调用`IHostTaskManager::BeginThreadAffinity`的调用上下文中<xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="37ded-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="37ded-124">当前任务必须不能重新安排对相应的调用直到[ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)。</span><span class="sxs-lookup"><span data-stu-id="37ded-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="37ded-125">任务可以切换出，但当它们返回切换时，必须将它们分配到同一操作系统线程从其断开。嵌套调用`BeginThreadAffinity`不起作用，因为该调用是指当前任务。</span><span class="sxs-lookup"><span data-stu-id="37ded-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ded-126">要求</span><span class="sxs-lookup"><span data-stu-id="37ded-126">Requirements</span></span>  
 <span data-ttu-id="37ded-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37ded-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37ded-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="37ded-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37ded-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="37ded-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37ded-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37ded-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ded-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="37ded-131">See also</span></span>
- [<span data-ttu-id="37ded-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="37ded-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="37ded-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="37ded-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="37ded-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="37ded-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="37ded-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="37ded-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
