---
title: ICLRTask::SetTaskIdentifier 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abd8848ed54b26b66090e4865f9c3a0e5c4d20db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078312"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="c2146-102">ICLRTask::SetTaskIdentifier 方法</span><span class="sxs-lookup"><span data-stu-id="c2146-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="c2146-103">指示公共语言运行时 (CLR) 将指定的标识符值与表示由当前的任务相关联[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="c2146-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2146-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2146-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2146-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2146-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="c2146-106">[in]公共语言运行时能够表示由当前的任务相关联的唯一标识符`ICLRTask`实例。</span><span class="sxs-lookup"><span data-stu-id="c2146-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2146-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c2146-107">Return Value</span></span>  
  
|<span data-ttu-id="c2146-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2146-108">HRESULT</span></span>|<span data-ttu-id="c2146-109">描述</span><span class="sxs-lookup"><span data-stu-id="c2146-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2146-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2146-110">S_OK</span></span>|<span data-ttu-id="c2146-111">`SetTaskIdentifier` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c2146-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="c2146-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2146-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2146-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c2146-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2146-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2146-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2146-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c2146-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2146-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2146-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2146-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c2146-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2146-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2146-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2146-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c2146-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2146-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2146-120">E_FAIL</span></span>|<span data-ttu-id="c2146-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c2146-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2146-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="c2146-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2146-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c2146-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2146-124">备注</span><span class="sxs-lookup"><span data-stu-id="c2146-124">Remarks</span></span>  
 <span data-ttu-id="c2146-125">主机可以将标识符关联的任务，以便帮助集成 CLR 和调试环境中的主机。</span><span class="sxs-lookup"><span data-stu-id="c2146-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="c2146-126">该标识符具有对 CLR 没有意义。</span><span class="sxs-lookup"><span data-stu-id="c2146-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="c2146-127">CLR 仅将它传递到调试器应用程序。</span><span class="sxs-lookup"><span data-stu-id="c2146-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="c2146-128">调试器可以使用此标识符将 CLR 调用堆栈与主机调用堆栈，相关联，并启用它们各自的跟踪信息时在调试器的用户界面中查看统一。</span><span class="sxs-lookup"><span data-stu-id="c2146-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2146-129">要求</span><span class="sxs-lookup"><span data-stu-id="c2146-129">Requirements</span></span>  
 <span data-ttu-id="c2146-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2146-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2146-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2146-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2146-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2146-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2146-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2146-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2146-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2146-134">See also</span></span>

- [<span data-ttu-id="c2146-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="c2146-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c2146-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c2146-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c2146-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="c2146-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c2146-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="c2146-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
