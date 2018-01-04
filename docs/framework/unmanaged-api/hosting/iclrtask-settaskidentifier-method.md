---
title: "ICLRTask::SetTaskIdentifier 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SetTaskIdentifier
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ace5b7b0153e9e019b56ebc2b7f5df0c5ed91d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="2e20c-102">ICLRTask::SetTaskIdentifier 方法</span><span class="sxs-lookup"><span data-stu-id="2e20c-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="2e20c-103">指示公共语言运行时 (CLR) 来表示由当前的任务相关联的指定的标识符值[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="2e20c-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e20c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e20c-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e20c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e20c-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="2e20c-106">[in]公共语言运行时，要表示由当前的任务相关联的唯一标识符`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="2e20c-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e20c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2e20c-107">Return Value</span></span>  
  
|<span data-ttu-id="2e20c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e20c-108">HRESULT</span></span>|<span data-ttu-id="2e20c-109">描述</span><span class="sxs-lookup"><span data-stu-id="2e20c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e20c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e20c-110">S_OK</span></span>|<span data-ttu-id="2e20c-111">`SetTaskIdentifier`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2e20c-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="2e20c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e20c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e20c-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2e20c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e20c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e20c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e20c-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="2e20c-115">The call timed out.</span></span>|  
|<span data-ttu-id="2e20c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e20c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e20c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2e20c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e20c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e20c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e20c-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2e20c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e20c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e20c-120">E_FAIL</span></span>|<span data-ttu-id="2e20c-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2e20c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e20c-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="2e20c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e20c-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2e20c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e20c-124">备注</span><span class="sxs-lookup"><span data-stu-id="2e20c-124">Remarks</span></span>  
 <span data-ttu-id="2e20c-125">主机可以将一个任务，来帮助将 CLR 和调试环境中的主机集成关联标识符。</span><span class="sxs-lookup"><span data-stu-id="2e20c-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="2e20c-126">该标识符具有对 CLR 没有意义。</span><span class="sxs-lookup"><span data-stu-id="2e20c-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="2e20c-127">CLR 将它传递到调试器应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e20c-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="2e20c-128">调试器可以使用此标识符将 CLR 调用堆栈的主机调用堆栈，与相关联，并使其各自的跟踪信息时在调试器的用户界面中查看统一。</span><span class="sxs-lookup"><span data-stu-id="2e20c-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e20c-129">惠?</span><span class="sxs-lookup"><span data-stu-id="2e20c-129">Requirements</span></span>  
 <span data-ttu-id="2e20c-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e20c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e20c-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e20c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e20c-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2e20c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e20c-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e20c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e20c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e20c-134">See Also</span></span>  
 [<span data-ttu-id="2e20c-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2e20c-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2e20c-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2e20c-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2e20c-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2e20c-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2e20c-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2e20c-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
