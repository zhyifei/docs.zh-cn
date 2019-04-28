---
title: ICLRTask::RudeAbort 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2db47f90e73922858013885e99e953ddcacbd450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763511"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="fc4da-102">ICLRTask::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="fc4da-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="fc4da-103">指示公共语言运行时 (CLR) 中止表示由当前的任务[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例立即和无条件地。</span><span class="sxs-lookup"><span data-stu-id="fc4da-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4da-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc4da-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="fc4da-105">返回值</span><span class="sxs-lookup"><span data-stu-id="fc4da-105">Return Value</span></span>  
  
|<span data-ttu-id="fc4da-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc4da-106">HRESULT</span></span>|<span data-ttu-id="fc4da-107">描述</span><span class="sxs-lookup"><span data-stu-id="fc4da-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc4da-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc4da-108">S_OK</span></span>|<span data-ttu-id="fc4da-109">`RudeAbort` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fc4da-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="fc4da-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc4da-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc4da-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fc4da-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc4da-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc4da-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc4da-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="fc4da-113">The call timed out.</span></span>|  
|<span data-ttu-id="fc4da-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc4da-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc4da-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fc4da-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc4da-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc4da-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc4da-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="fc4da-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc4da-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc4da-118">E_FAIL</span></span>|<span data-ttu-id="fc4da-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fc4da-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc4da-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="fc4da-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc4da-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fc4da-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc4da-122">备注</span><span class="sxs-lookup"><span data-stu-id="fc4da-122">Remarks</span></span>  
 <span data-ttu-id="fc4da-123">主机调用`RudeAbort`立即中止任务。</span><span class="sxs-lookup"><span data-stu-id="fc4da-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="fc4da-124">终结器和异常处理例程不保证执行。</span><span class="sxs-lookup"><span data-stu-id="fc4da-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc4da-125">要求</span><span class="sxs-lookup"><span data-stu-id="fc4da-125">Requirements</span></span>  
 <span data-ttu-id="fc4da-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc4da-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc4da-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc4da-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc4da-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fc4da-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc4da-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc4da-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc4da-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc4da-130">See also</span></span>

- [<span data-ttu-id="fc4da-131">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="fc4da-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fc4da-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="fc4da-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fc4da-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="fc4da-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fc4da-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="fc4da-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
