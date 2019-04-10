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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147610"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="ef734-102">ICLRTask::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="ef734-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="ef734-103">指示公共语言运行时 (CLR) 中止表示由当前的任务[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例立即和无条件地。</span><span class="sxs-lookup"><span data-stu-id="ef734-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef734-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef734-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="ef734-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ef734-105">Return Value</span></span>  
  
|<span data-ttu-id="ef734-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef734-106">HRESULT</span></span>|<span data-ttu-id="ef734-107">描述</span><span class="sxs-lookup"><span data-stu-id="ef734-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef734-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef734-108">S_OK</span></span>|`RudeAbort` <span data-ttu-id="ef734-109">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ef734-109">returned successfully.</span></span>|  
|<span data-ttu-id="ef734-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef734-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef734-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ef734-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef734-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ef734-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ef734-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ef734-113">The call timed out.</span></span>|  
|<span data-ttu-id="ef734-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ef734-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ef734-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ef734-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ef734-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ef734-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ef734-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ef734-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ef734-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef734-118">E_FAIL</span></span>|<span data-ttu-id="ef734-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ef734-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef734-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="ef734-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef734-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ef734-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef734-122">备注</span><span class="sxs-lookup"><span data-stu-id="ef734-122">Remarks</span></span>  
 <span data-ttu-id="ef734-123">主机调用`RudeAbort`立即中止任务。</span><span class="sxs-lookup"><span data-stu-id="ef734-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="ef734-124">终结器和异常处理例程不保证执行。</span><span class="sxs-lookup"><span data-stu-id="ef734-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef734-125">要求</span><span class="sxs-lookup"><span data-stu-id="ef734-125">Requirements</span></span>  
 <span data-ttu-id="ef734-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef734-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef734-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef734-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef734-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ef734-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ef734-129">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ef734-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef734-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef734-130">See also</span></span>

- [<span data-ttu-id="ef734-131">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="ef734-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ef734-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ef734-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ef734-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="ef734-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ef734-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ef734-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
