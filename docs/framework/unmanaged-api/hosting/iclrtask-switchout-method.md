---
title: ICLRTask::SwitchOut 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a215189461bd22011462842bf02ff6c0109119fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090030"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="1a8d3-102">ICLRTask::SwitchOut 方法</span><span class="sxs-lookup"><span data-stu-id="1a8d3-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="1a8d3-103">通知任务的当前表示公共语言运行时 (CLR) [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例不再处于可操作状态。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a8d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a8d3-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1a8d3-105">返回值</span><span class="sxs-lookup"><span data-stu-id="1a8d3-105">Return Value</span></span>  
  
|<span data-ttu-id="1a8d3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a8d3-106">HRESULT</span></span>|<span data-ttu-id="1a8d3-107">描述</span><span class="sxs-lookup"><span data-stu-id="1a8d3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a8d3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a8d3-108">S_OK</span></span>|<span data-ttu-id="1a8d3-109">`SwitchOut` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="1a8d3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1a8d3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1a8d3-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1a8d3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1a8d3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1a8d3-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-113">The call timed out.</span></span>|  
|<span data-ttu-id="1a8d3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1a8d3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1a8d3-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1a8d3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1a8d3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1a8d3-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1a8d3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1a8d3-118">E_FAIL</span></span>|<span data-ttu-id="1a8d3-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1a8d3-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1a8d3-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a8d3-122">备注</span><span class="sxs-lookup"><span data-stu-id="1a8d3-122">Remarks</span></span>  
 <span data-ttu-id="1a8d3-123">主机可调用`SwitchOut`以通知 CLR，它已暂时停止执行的任务的当前`ICLRTask`实例所表示，并将重新计划任务。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a8d3-124">要求</span><span class="sxs-lookup"><span data-stu-id="1a8d3-124">Requirements</span></span>  
 <span data-ttu-id="1a8d3-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a8d3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a8d3-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1a8d3-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a8d3-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1a8d3-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a8d3-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8d3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8d3-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a8d3-129">See also</span></span>

- [<span data-ttu-id="1a8d3-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1a8d3-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1a8d3-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1a8d3-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1a8d3-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1a8d3-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1a8d3-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1a8d3-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
