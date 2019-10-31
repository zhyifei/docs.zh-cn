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
ms.openlocfilehash: f9c2e77013ff9e31a0a2ef3b4ca511b76ae345e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124596"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="9af66-102">ICLRTask::SwitchOut 方法</span><span class="sxs-lookup"><span data-stu-id="9af66-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="9af66-103">通知公共语言运行时（CLR）当前[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例表示的任务不再处于可运行状态。</span><span class="sxs-lookup"><span data-stu-id="9af66-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9af66-104">语法</span><span class="sxs-lookup"><span data-stu-id="9af66-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9af66-105">返回值</span><span class="sxs-lookup"><span data-stu-id="9af66-105">Return Value</span></span>  
  
|<span data-ttu-id="9af66-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9af66-106">HRESULT</span></span>|<span data-ttu-id="9af66-107">描述</span><span class="sxs-lookup"><span data-stu-id="9af66-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9af66-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9af66-108">S_OK</span></span>|<span data-ttu-id="9af66-109">`SwitchOut` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="9af66-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="9af66-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9af66-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9af66-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9af66-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9af66-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9af66-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9af66-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9af66-113">The call timed out.</span></span>|  
|<span data-ttu-id="9af66-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9af66-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9af66-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9af66-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9af66-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9af66-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9af66-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9af66-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9af66-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9af66-118">E_FAIL</span></span>|<span data-ttu-id="9af66-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9af66-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9af66-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9af66-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9af66-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9af66-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9af66-122">备注</span><span class="sxs-lookup"><span data-stu-id="9af66-122">Remarks</span></span>  
 <span data-ttu-id="9af66-123">主机调用 `SwitchOut`，通知 CLR 它已暂时停止执行当前 `ICLRTask` 实例表示的任务，并将重新计划任务。</span><span class="sxs-lookup"><span data-stu-id="9af66-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9af66-124">要求</span><span class="sxs-lookup"><span data-stu-id="9af66-124">Requirements</span></span>  
 <span data-ttu-id="9af66-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9af66-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9af66-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9af66-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9af66-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9af66-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9af66-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9af66-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af66-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9af66-129">See also</span></span>

- [<span data-ttu-id="9af66-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="9af66-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9af66-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9af66-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9af66-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="9af66-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9af66-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="9af66-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
