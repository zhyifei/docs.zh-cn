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
ms.openlocfilehash: aacf9de36dc39b63ed36b672e31f40704413d608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176326"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="2cdce-102">ICLRTask::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="2cdce-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="2cdce-103">指示通用语言运行时 （CLR） 立即无条件中止由当前[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示的任务。</span><span class="sxs-lookup"><span data-stu-id="2cdce-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdce-104">语法</span><span class="sxs-lookup"><span data-stu-id="2cdce-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="2cdce-105">返回值</span><span class="sxs-lookup"><span data-stu-id="2cdce-105">Return Value</span></span>  
  
|<span data-ttu-id="2cdce-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2cdce-106">HRESULT</span></span>|<span data-ttu-id="2cdce-107">说明</span><span class="sxs-lookup"><span data-stu-id="2cdce-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cdce-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cdce-108">S_OK</span></span>|<span data-ttu-id="2cdce-109">`RudeAbort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2cdce-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="2cdce-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2cdce-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2cdce-111">CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2cdce-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2cdce-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2cdce-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2cdce-113">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="2cdce-113">The call timed out.</span></span>|  
|<span data-ttu-id="2cdce-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2cdce-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2cdce-115">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="2cdce-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2cdce-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2cdce-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2cdce-117">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="2cdce-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2cdce-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2cdce-118">E_FAIL</span></span>|<span data-ttu-id="2cdce-119">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2cdce-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2cdce-120">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="2cdce-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2cdce-121">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2cdce-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cdce-122">备注</span><span class="sxs-lookup"><span data-stu-id="2cdce-122">Remarks</span></span>  
 <span data-ttu-id="2cdce-123">主机调用`RudeAbort`以立即中止任务。</span><span class="sxs-lookup"><span data-stu-id="2cdce-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="2cdce-124">不保证执行终结者和异常处理例程。</span><span class="sxs-lookup"><span data-stu-id="2cdce-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cdce-125">要求</span><span class="sxs-lookup"><span data-stu-id="2cdce-125">Requirements</span></span>  
 <span data-ttu-id="2cdce-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2cdce-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cdce-127">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2cdce-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2cdce-128">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="2cdce-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cdce-129">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cdce-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdce-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cdce-130">See also</span></span>

- [<span data-ttu-id="2cdce-131">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2cdce-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2cdce-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2cdce-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2cdce-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2cdce-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2cdce-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2cdce-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
