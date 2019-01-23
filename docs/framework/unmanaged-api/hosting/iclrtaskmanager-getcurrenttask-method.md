---
title: ICLRTaskManager::GetCurrentTask 方法
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 164c5941587d91fa807827b8783260fa34a8ef66
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492397"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="1b3c8-102">ICLRTaskManager::GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="1b3c8-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="1b3c8-103">获取[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)方法调用产生的操作系统线程当前正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b3c8-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b3c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="1b3c8-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="1b3c8-106">[out]指向的地址的指针`ICLRTask`从中发起调用，在操作系统线程当前正在执行的实例或如果没有任何任务当前正在此线程上执行，则为 null。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b3c8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1b3c8-107">Return Value</span></span>  
  
|<span data-ttu-id="1b3c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b3c8-108">HRESULT</span></span>|<span data-ttu-id="1b3c8-109">描述</span><span class="sxs-lookup"><span data-stu-id="1b3c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b3c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b3c8-110">S_OK</span></span>|<span data-ttu-id="1b3c8-111">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="1b3c8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b3c8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b3c8-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b3c8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b3c8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b3c8-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-115">The call timed out.</span></span>|  
|<span data-ttu-id="1b3c8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b3c8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b3c8-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b3c8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b3c8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b3c8-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b3c8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b3c8-120">E_FAIL</span></span>|<span data-ttu-id="1b3c8-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b3c8-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b3c8-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b3c8-124">备注</span><span class="sxs-lookup"><span data-stu-id="1b3c8-124">Remarks</span></span>  
 <span data-ttu-id="1b3c8-125">`ICLRTask`实例的`ppTask`参数指向表示当前执行的任务的 clr。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="1b3c8-126">`ICLRTask`实例都与相应关联[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)表示任务主机的实例。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b3c8-127">要求</span><span class="sxs-lookup"><span data-stu-id="1b3c8-127">Requirements</span></span>  
 <span data-ttu-id="1b3c8-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b3c8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3c8-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b3c8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b3c8-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b3c8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b3c8-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3c8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3c8-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b3c8-132">See also</span></span>
- [<span data-ttu-id="1b3c8-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1b3c8-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1b3c8-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1b3c8-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1b3c8-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1b3c8-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1b3c8-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1b3c8-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
