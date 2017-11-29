---
title: "ICLRTask::Abort 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Abort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e789afc8f570d647fd44f8f43c23c2cc33ba8f70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="ea202-102">ICLRTask::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="ea202-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="ea202-103">请求公共语言运行时 (CLR) 中止任务的当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示。</span><span class="sxs-lookup"><span data-stu-id="ea202-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea202-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea202-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ea202-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ea202-105">Return Value</span></span>  
  
|<span data-ttu-id="ea202-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea202-106">HRESULT</span></span>|<span data-ttu-id="ea202-107">描述</span><span class="sxs-lookup"><span data-stu-id="ea202-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea202-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea202-108">S_OK</span></span>|<span data-ttu-id="ea202-109">`Abort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ea202-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="ea202-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ea202-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea202-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ea202-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea202-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea202-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea202-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ea202-113">The call timed out.</span></span>|  
|<span data-ttu-id="ea202-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea202-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea202-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ea202-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea202-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea202-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea202-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ea202-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea202-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea202-118">E_FAIL</span></span>|<span data-ttu-id="ea202-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ea202-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea202-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="ea202-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea202-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ea202-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea202-122">备注</span><span class="sxs-lookup"><span data-stu-id="ea202-122">Remarks</span></span>  
 <span data-ttu-id="ea202-123">CLR 引发<xref:System.Threading.ThreadAbortException>主机时调用`Abort`。</span><span class="sxs-lookup"><span data-stu-id="ea202-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="ea202-124">它将返回异常信息初始化，而无需等待用户代码，例如终结器或异常处理机制，以执行后立即。</span><span class="sxs-lookup"><span data-stu-id="ea202-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="ea202-125">调用`Abort`因此很快返回。</span><span class="sxs-lookup"><span data-stu-id="ea202-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea202-126">要求</span><span class="sxs-lookup"><span data-stu-id="ea202-126">Requirements</span></span>  
 <span data-ttu-id="ea202-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea202-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea202-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea202-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea202-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ea202-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea202-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea202-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea202-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea202-131">See Also</span></span>  
 [<span data-ttu-id="ea202-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="ea202-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ea202-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ea202-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ea202-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="ea202-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ea202-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ea202-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
