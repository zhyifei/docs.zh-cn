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
ms.openlocfilehash: 7c4b6780b9784c5d02499224e6787f2cda6cc8e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442827"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="faaf9-102">IHostTaskManager::SwitchToTask 方法</span><span class="sxs-lookup"><span data-stu-id="faaf9-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="faaf9-103">通知主机应该换出当前任务。</span><span class="sxs-lookup"><span data-stu-id="faaf9-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faaf9-104">语法</span><span class="sxs-lookup"><span data-stu-id="faaf9-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="faaf9-105">参数</span><span class="sxs-lookup"><span data-stu-id="faaf9-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="faaf9-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)枚举值，指示主机时应采取的操作的请求的操作块。</span><span class="sxs-lookup"><span data-stu-id="faaf9-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faaf9-107">返回值</span><span class="sxs-lookup"><span data-stu-id="faaf9-107">Return Value</span></span>  
  
|<span data-ttu-id="faaf9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faaf9-108">HRESULT</span></span>|<span data-ttu-id="faaf9-109">描述</span><span class="sxs-lookup"><span data-stu-id="faaf9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faaf9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="faaf9-110">S_OK</span></span>|<span data-ttu-id="faaf9-111">`SwitchToTask` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="faaf9-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="faaf9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="faaf9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="faaf9-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="faaf9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="faaf9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="faaf9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="faaf9-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="faaf9-115">The call timed out.</span></span>|  
|<span data-ttu-id="faaf9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="faaf9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="faaf9-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="faaf9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="faaf9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="faaf9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="faaf9-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="faaf9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="faaf9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faaf9-120">E_FAIL</span></span>|<span data-ttu-id="faaf9-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="faaf9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="faaf9-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="faaf9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="faaf9-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="faaf9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faaf9-124">备注</span><span class="sxs-lookup"><span data-stu-id="faaf9-124">Remarks</span></span>  
 <span data-ttu-id="faaf9-125">主机可以在为所需的或所需的另一个任务切换。</span><span class="sxs-lookup"><span data-stu-id="faaf9-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="faaf9-126">`SwitchToTask` 未指定主机应切换到; 的任务它指定它应从切换任务。</span><span class="sxs-lookup"><span data-stu-id="faaf9-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faaf9-127">要求</span><span class="sxs-lookup"><span data-stu-id="faaf9-127">Requirements</span></span>  
 <span data-ttu-id="faaf9-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faaf9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faaf9-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="faaf9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faaf9-130">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="faaf9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="faaf9-131">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faaf9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faaf9-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="faaf9-132">See Also</span></span>  
 [<span data-ttu-id="faaf9-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="faaf9-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="faaf9-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="faaf9-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="faaf9-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="faaf9-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="faaf9-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="faaf9-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
