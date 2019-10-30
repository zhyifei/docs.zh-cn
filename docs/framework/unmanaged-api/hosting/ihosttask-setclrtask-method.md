---
title: IHostTask::SetCLRTask 方法
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121366"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="01814-102">IHostTask::SetCLRTask 方法</span><span class="sxs-lookup"><span data-stu-id="01814-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="01814-103">将 `ICLRTask` 实例与当前[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)实例相关联。</span><span class="sxs-lookup"><span data-stu-id="01814-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01814-104">语法</span><span class="sxs-lookup"><span data-stu-id="01814-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01814-105">参数</span><span class="sxs-lookup"><span data-stu-id="01814-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="01814-106">中指向要与当前 `IHostTask` 实例相关联的 `ICLRTask` 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="01814-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01814-107">返回值</span><span class="sxs-lookup"><span data-stu-id="01814-107">Return Value</span></span>  
  
|<span data-ttu-id="01814-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01814-108">HRESULT</span></span>|<span data-ttu-id="01814-109">描述</span><span class="sxs-lookup"><span data-stu-id="01814-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01814-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="01814-110">S_OK</span></span>|<span data-ttu-id="01814-111">`SetCLRTask` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="01814-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="01814-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01814-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01814-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="01814-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01814-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01814-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01814-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="01814-115">The call timed out.</span></span>|  
|<span data-ttu-id="01814-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01814-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01814-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="01814-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01814-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01814-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01814-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="01814-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01814-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01814-120">E_FAIL</span></span>|<span data-ttu-id="01814-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="01814-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01814-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="01814-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01814-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="01814-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01814-124">备注</span><span class="sxs-lookup"><span data-stu-id="01814-124">Remarks</span></span>  
 <span data-ttu-id="01814-125">CLR 调用 `SetCLRTask` 将 `ICLRTask` 实例与当前 `IHostTask` 实例（通过调用[IHostTaskManager：： CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)创建）关联。</span><span class="sxs-lookup"><span data-stu-id="01814-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01814-126">要求</span><span class="sxs-lookup"><span data-stu-id="01814-126">Requirements</span></span>  
 <span data-ttu-id="01814-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01814-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01814-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01814-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01814-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="01814-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01814-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01814-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01814-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="01814-131">See also</span></span>

- [<span data-ttu-id="01814-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="01814-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="01814-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="01814-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="01814-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="01814-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="01814-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="01814-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
