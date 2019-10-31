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
ms.openlocfilehash: 7c157cf27d2fe86288024a6c35e6dcbea3c46347
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133105"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="08b08-102">IHostTaskManager::BeginThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="08b08-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="08b08-103">通知宿主托管代码正在输入一个时间段，在此期间，不能将当前任务移动到另一个操作系统线程。</span><span class="sxs-lookup"><span data-stu-id="08b08-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b08-104">语法</span><span class="sxs-lookup"><span data-stu-id="08b08-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="08b08-105">返回值</span><span class="sxs-lookup"><span data-stu-id="08b08-105">Return Value</span></span>  
  
|<span data-ttu-id="08b08-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08b08-106">HRESULT</span></span>|<span data-ttu-id="08b08-107">描述</span><span class="sxs-lookup"><span data-stu-id="08b08-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08b08-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="08b08-108">S_OK</span></span>|<span data-ttu-id="08b08-109">`BeginThreadAffinity` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="08b08-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="08b08-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08b08-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08b08-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="08b08-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08b08-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08b08-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08b08-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="08b08-113">The call timed out.</span></span>|  
|<span data-ttu-id="08b08-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08b08-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08b08-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="08b08-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08b08-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08b08-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08b08-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="08b08-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08b08-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08b08-118">E_FAIL</span></span>|<span data-ttu-id="08b08-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="08b08-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08b08-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="08b08-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08b08-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="08b08-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08b08-122">备注</span><span class="sxs-lookup"><span data-stu-id="08b08-122">Remarks</span></span>  
 <span data-ttu-id="08b08-123">CLR 通常在对 <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>的调用的上下文中调用 `IHostTaskManager::BeginThreadAffinity`。</span><span class="sxs-lookup"><span data-stu-id="08b08-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="08b08-124">在对[IHostTaskManager：： EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)进行相应的调用之前，不能重新计划当前任务。</span><span class="sxs-lookup"><span data-stu-id="08b08-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="08b08-125">可以切换出任务，但当它们切换回时，必须将它们分配到从中进行切换的相同操作系统线程。对 `BeginThreadAffinity` 的嵌套调用不起作用，因为调用指的是当前任务。</span><span class="sxs-lookup"><span data-stu-id="08b08-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b08-126">要求</span><span class="sxs-lookup"><span data-stu-id="08b08-126">Requirements</span></span>  
 <span data-ttu-id="08b08-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08b08-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08b08-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="08b08-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08b08-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="08b08-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08b08-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b08-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b08-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="08b08-131">See also</span></span>

- [<span data-ttu-id="08b08-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="08b08-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="08b08-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="08b08-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="08b08-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="08b08-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="08b08-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="08b08-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
