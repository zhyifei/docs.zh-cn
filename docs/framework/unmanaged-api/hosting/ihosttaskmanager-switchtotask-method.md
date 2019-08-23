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
ms.openlocfilehash: 4af3d73a4c45654d1d40ef2fbf44a0e2b3e1bf32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913718"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="8e00a-102">IHostTaskManager::SwitchToTask 方法</span><span class="sxs-lookup"><span data-stu-id="8e00a-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="8e00a-103">通知宿主应切换到当前任务。</span><span class="sxs-lookup"><span data-stu-id="8e00a-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e00a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e00a-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e00a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e00a-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="8e00a-106">中[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)枚举值之一, 指示请求的操作阻止时主机应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8e00a-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e00a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8e00a-107">Return Value</span></span>  
  
|<span data-ttu-id="8e00a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e00a-108">HRESULT</span></span>|<span data-ttu-id="8e00a-109">描述</span><span class="sxs-lookup"><span data-stu-id="8e00a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e00a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e00a-110">S_OK</span></span>|<span data-ttu-id="8e00a-111">`SwitchToTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8e00a-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="8e00a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e00a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e00a-113">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8e00a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e00a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e00a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e00a-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8e00a-115">The call timed out.</span></span>|  
|<span data-ttu-id="8e00a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e00a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e00a-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8e00a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e00a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e00a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e00a-119">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8e00a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e00a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e00a-120">E_FAIL</span></span>|<span data-ttu-id="8e00a-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8e00a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e00a-122">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8e00a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e00a-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8e00a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e00a-124">备注</span><span class="sxs-lookup"><span data-stu-id="8e00a-124">Remarks</span></span>  
 <span data-ttu-id="8e00a-125">宿主可以根据需要切换到其他任务。</span><span class="sxs-lookup"><span data-stu-id="8e00a-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e00a-126">`SwitchToTask`不指定宿主应切换到的任务;它仅指定应从其切换的任务。</span><span class="sxs-lookup"><span data-stu-id="8e00a-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e00a-127">要求</span><span class="sxs-lookup"><span data-stu-id="8e00a-127">Requirements</span></span>  
 <span data-ttu-id="8e00a-128">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e00a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e00a-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e00a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e00a-130">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8e00a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e00a-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e00a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e00a-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e00a-132">See also</span></span>

- [<span data-ttu-id="8e00a-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="8e00a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8e00a-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e00a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8e00a-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="8e00a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8e00a-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e00a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
