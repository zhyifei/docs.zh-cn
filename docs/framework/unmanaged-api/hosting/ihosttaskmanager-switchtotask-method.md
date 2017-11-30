---
title: "IHostTaskManager::SwitchToTask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SwitchToTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b85c762bd2d10baddfa013a8310e3b542a94af6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="cd943-102">IHostTaskManager::SwitchToTask 方法</span><span class="sxs-lookup"><span data-stu-id="cd943-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="cd943-103">通知主机应该换出当前任务。</span><span class="sxs-lookup"><span data-stu-id="cd943-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd943-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd943-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd943-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd943-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="cd943-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)枚举值，指示主机时应采取的操作的请求的操作块。</span><span class="sxs-lookup"><span data-stu-id="cd943-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd943-107">返回值</span><span class="sxs-lookup"><span data-stu-id="cd943-107">Return Value</span></span>  
  
|<span data-ttu-id="cd943-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd943-108">HRESULT</span></span>|<span data-ttu-id="cd943-109">描述</span><span class="sxs-lookup"><span data-stu-id="cd943-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd943-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd943-110">S_OK</span></span>|<span data-ttu-id="cd943-111">`SwitchToTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="cd943-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="cd943-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd943-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd943-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="cd943-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd943-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd943-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd943-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="cd943-115">The call timed out.</span></span>|  
|<span data-ttu-id="cd943-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd943-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd943-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="cd943-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd943-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd943-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd943-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="cd943-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd943-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd943-120">E_FAIL</span></span>|<span data-ttu-id="cd943-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="cd943-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd943-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="cd943-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd943-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="cd943-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd943-124">备注</span><span class="sxs-lookup"><span data-stu-id="cd943-124">Remarks</span></span>  
 <span data-ttu-id="cd943-125">主机可以在为所需的或所需的另一个任务切换。</span><span class="sxs-lookup"><span data-stu-id="cd943-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd943-126">`SwitchToTask`未指定主机应切换到; 的任务它指定它应从切换任务。</span><span class="sxs-lookup"><span data-stu-id="cd943-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd943-127">要求</span><span class="sxs-lookup"><span data-stu-id="cd943-127">Requirements</span></span>  
 <span data-ttu-id="cd943-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd943-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd943-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd943-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd943-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cd943-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd943-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd943-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd943-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd943-132">See Also</span></span>  
 [<span data-ttu-id="cd943-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="cd943-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="cd943-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="cd943-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="cd943-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="cd943-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="cd943-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="cd943-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
