---
title: IHostTaskManager::SwitchToTask 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a50c9f7fc5921d3e5c21dd3566de81ac2249f3dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796599"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="111bf-102">IHostTaskManager::SwitchToTask 方法</span><span class="sxs-lookup"><span data-stu-id="111bf-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="111bf-103">通知主机应切换当前任务。</span><span class="sxs-lookup"><span data-stu-id="111bf-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="111bf-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="111bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="111bf-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="111bf-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)枚举值，它指示主机时应采取的操作的请求的操作块。</span><span class="sxs-lookup"><span data-stu-id="111bf-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="111bf-107">返回值</span><span class="sxs-lookup"><span data-stu-id="111bf-107">Return Value</span></span>  
  
|<span data-ttu-id="111bf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="111bf-108">HRESULT</span></span>|<span data-ttu-id="111bf-109">描述</span><span class="sxs-lookup"><span data-stu-id="111bf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="111bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="111bf-110">S_OK</span></span>|<span data-ttu-id="111bf-111">`SwitchToTask` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="111bf-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="111bf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="111bf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="111bf-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="111bf-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="111bf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="111bf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="111bf-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="111bf-115">The call timed out.</span></span>|  
|<span data-ttu-id="111bf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="111bf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="111bf-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="111bf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="111bf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="111bf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="111bf-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="111bf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="111bf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="111bf-120">E_FAIL</span></span>|<span data-ttu-id="111bf-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="111bf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="111bf-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="111bf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="111bf-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="111bf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="111bf-124">备注</span><span class="sxs-lookup"><span data-stu-id="111bf-124">Remarks</span></span>  
 <span data-ttu-id="111bf-125">主机可以在作为所需的或所需的另一个任务切换。</span><span class="sxs-lookup"><span data-stu-id="111bf-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="111bf-126">`SwitchToTask` 未指定主机应切换到; 的任务它指定只应从切换任务。</span><span class="sxs-lookup"><span data-stu-id="111bf-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="111bf-127">要求</span><span class="sxs-lookup"><span data-stu-id="111bf-127">Requirements</span></span>  
 <span data-ttu-id="111bf-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="111bf-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111bf-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="111bf-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="111bf-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="111bf-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="111bf-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111bf-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111bf-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="111bf-132">See also</span></span>

- [<span data-ttu-id="111bf-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="111bf-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="111bf-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="111bf-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="111bf-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="111bf-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="111bf-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="111bf-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
