---
title: IHostTask::Join 方法
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4373fc4e8a4c414c40e8d3c5547b5998b9300348
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789514"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="cc6cd-102">IHostTask::Join 方法</span><span class="sxs-lookup"><span data-stu-id="cc6cd-102">IHostTask::Join Method</span></span>
<span data-ttu-id="cc6cd-103">阻止，直到表示由当前的任务调用任务[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例完成后，指定的时间间隔结束，或[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)调用。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc6cd-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc6cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc6cd-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="cc6cd-106">[in]时间间隔，以毫秒为单位，以等待任务终止。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="cc6cd-107">如果此时间间隔过后任务终止之前，将取消阻止调用任务。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="cc6cd-108">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="cc6cd-109">值为 WAIT_ALERTABLE 指示如果唤醒任务主机`Alert`之前调用`milliseconds`结束。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc6cd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cc6cd-110">Return Value</span></span>  
  
|<span data-ttu-id="cc6cd-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc6cd-111">HRESULT</span></span>|<span data-ttu-id="cc6cd-112">描述</span><span class="sxs-lookup"><span data-stu-id="cc6cd-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc6cd-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc6cd-113">S_OK</span></span>|<span data-ttu-id="cc6cd-114">`Join` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="cc6cd-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc6cd-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc6cd-116">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc6cd-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc6cd-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc6cd-118">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-118">The call timed out.</span></span>|  
|<span data-ttu-id="cc6cd-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc6cd-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc6cd-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc6cd-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc6cd-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc6cd-122">事件已取消时被阻塞的线程或纤程正在等待它，或当前`IHostTask`实例不是与任务关联。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="cc6cd-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc6cd-123">E_FAIL</span></span>|<span data-ttu-id="cc6cd-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc6cd-125">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc6cd-126">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc6cd-127">要求</span><span class="sxs-lookup"><span data-stu-id="cc6cd-127">Requirements</span></span>  
 <span data-ttu-id="cc6cd-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc6cd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc6cd-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cc6cd-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc6cd-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cc6cd-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc6cd-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc6cd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6cd-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc6cd-132">See also</span></span>

- [<span data-ttu-id="cc6cd-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="cc6cd-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cc6cd-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="cc6cd-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cc6cd-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="cc6cd-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cc6cd-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="cc6cd-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="cc6cd-137">WAIT_OPTION 枚举</span><span class="sxs-lookup"><span data-stu-id="cc6cd-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
