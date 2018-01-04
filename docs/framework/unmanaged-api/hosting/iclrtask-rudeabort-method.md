---
title: "ICLRTask::RudeAbort 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.RudeAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f48de1fb44d978b1d9c8960c3e44c360b0801e27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="49ef6-102">ICLRTask::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="49ef6-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="49ef6-103">指示公共语言运行时 (CLR) 中止表示由当前的任务[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例立即和无条件地。</span><span class="sxs-lookup"><span data-stu-id="49ef6-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ef6-104">语法</span><span class="sxs-lookup"><span data-stu-id="49ef6-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="49ef6-105">返回值</span><span class="sxs-lookup"><span data-stu-id="49ef6-105">Return Value</span></span>  
  
|<span data-ttu-id="49ef6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49ef6-106">HRESULT</span></span>|<span data-ttu-id="49ef6-107">描述</span><span class="sxs-lookup"><span data-stu-id="49ef6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49ef6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="49ef6-108">S_OK</span></span>|<span data-ttu-id="49ef6-109">`RudeAbort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="49ef6-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="49ef6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49ef6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49ef6-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="49ef6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49ef6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49ef6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49ef6-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="49ef6-113">The call timed out.</span></span>|  
|<span data-ttu-id="49ef6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49ef6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49ef6-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="49ef6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49ef6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49ef6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49ef6-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="49ef6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49ef6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49ef6-118">E_FAIL</span></span>|<span data-ttu-id="49ef6-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="49ef6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49ef6-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="49ef6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49ef6-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="49ef6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49ef6-122">备注</span><span class="sxs-lookup"><span data-stu-id="49ef6-122">Remarks</span></span>  
 <span data-ttu-id="49ef6-123">主机可调用`RudeAbort`立即中止的任务。</span><span class="sxs-lookup"><span data-stu-id="49ef6-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="49ef6-124">终结器和异常处理例程不保证要执行。</span><span class="sxs-lookup"><span data-stu-id="49ef6-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49ef6-125">惠?</span><span class="sxs-lookup"><span data-stu-id="49ef6-125">Requirements</span></span>  
 <span data-ttu-id="49ef6-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49ef6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49ef6-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="49ef6-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49ef6-128">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="49ef6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49ef6-129">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49ef6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ef6-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="49ef6-130">See Also</span></span>  
 [<span data-ttu-id="49ef6-131">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="49ef6-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="49ef6-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="49ef6-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="49ef6-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="49ef6-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="49ef6-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="49ef6-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
