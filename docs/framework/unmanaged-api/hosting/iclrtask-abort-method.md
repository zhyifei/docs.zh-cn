---
title: ICLRTask::Abort 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: 026d4c14abed030b80e8e1b3f8363fbd59ac05e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124909"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="b7540-102">ICLRTask::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="b7540-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="b7540-103">请求公共语言运行时（CLR）中止当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示的任务。</span><span class="sxs-lookup"><span data-stu-id="b7540-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7540-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7540-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b7540-105">返回值</span><span class="sxs-lookup"><span data-stu-id="b7540-105">Return Value</span></span>  
  
|<span data-ttu-id="b7540-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7540-106">HRESULT</span></span>|<span data-ttu-id="b7540-107">描述</span><span class="sxs-lookup"><span data-stu-id="b7540-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7540-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7540-108">S_OK</span></span>|<span data-ttu-id="b7540-109">`Abort` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="b7540-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="b7540-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7540-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7540-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b7540-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7540-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7540-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7540-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b7540-113">The call timed out.</span></span>|  
|<span data-ttu-id="b7540-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7540-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7540-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b7540-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7540-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7540-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7540-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b7540-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7540-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7540-118">E_FAIL</span></span>|<span data-ttu-id="b7540-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b7540-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7540-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b7540-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7540-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b7540-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7540-122">备注</span><span class="sxs-lookup"><span data-stu-id="b7540-122">Remarks</span></span>  
 <span data-ttu-id="b7540-123">当主机调用 `Abort`时，CLR 将引发 <xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="b7540-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="b7540-124">它在异常信息初始化后立即返回，而不会等待执行用户代码（如终结器或异常处理机制）。</span><span class="sxs-lookup"><span data-stu-id="b7540-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="b7540-125">因此，对 `Abort` 的调用会迅速返回。</span><span class="sxs-lookup"><span data-stu-id="b7540-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7540-126">要求</span><span class="sxs-lookup"><span data-stu-id="b7540-126">Requirements</span></span>  
 <span data-ttu-id="b7540-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7540-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7540-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7540-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7540-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b7540-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7540-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7540-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7540-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7540-131">See also</span></span>

- [<span data-ttu-id="b7540-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="b7540-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b7540-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b7540-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b7540-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="b7540-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b7540-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b7540-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
