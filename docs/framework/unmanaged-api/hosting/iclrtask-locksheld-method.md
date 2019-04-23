---
title: ICLRTask::LocksHeld 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f548d8b19a76aaccbae276dd63f091e4488690b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106803"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="a46af-102">ICLRTask::LocksHeld 方法</span><span class="sxs-lookup"><span data-stu-id="a46af-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="a46af-103">获取当前任务上持有的锁数。</span><span class="sxs-lookup"><span data-stu-id="a46af-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a46af-104">语法</span><span class="sxs-lookup"><span data-stu-id="a46af-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a46af-105">参数</span><span class="sxs-lookup"><span data-stu-id="a46af-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="a46af-106">[out]在方法调用时，该任务保留的锁数。</span><span class="sxs-lookup"><span data-stu-id="a46af-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a46af-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a46af-107">Return Value</span></span>  
  
|<span data-ttu-id="a46af-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a46af-108">HRESULT</span></span>|<span data-ttu-id="a46af-109">描述</span><span class="sxs-lookup"><span data-stu-id="a46af-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a46af-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a46af-110">S_OK</span></span>|<span data-ttu-id="a46af-111">`LocksHeld` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a46af-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="a46af-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a46af-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a46af-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a46af-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a46af-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a46af-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a46af-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="a46af-115">The call timed out.</span></span>|  
|<span data-ttu-id="a46af-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a46af-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a46af-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a46af-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a46af-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a46af-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a46af-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a46af-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a46af-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a46af-120">E_FAIL</span></span>|<span data-ttu-id="a46af-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a46af-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a46af-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="a46af-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a46af-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a46af-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a46af-124">要求</span><span class="sxs-lookup"><span data-stu-id="a46af-124">Requirements</span></span>  
 <span data-ttu-id="a46af-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a46af-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a46af-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a46af-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a46af-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a46af-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a46af-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a46af-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46af-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a46af-129">See also</span></span>

- [<span data-ttu-id="a46af-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="a46af-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a46af-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a46af-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a46af-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a46af-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a46af-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a46af-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
