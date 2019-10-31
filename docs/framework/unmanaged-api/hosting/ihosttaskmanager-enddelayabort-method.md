---
title: IHostTaskManager::EndDelayAbort 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: cf79c0d0f6def46d7f4d55f17afbd1f1dff00ad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133075"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="67ab0-102">IHostTaskManager::EndDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="67ab0-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="67ab0-103">在之前调用[IHostTaskManager：： BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)时，通知宿主托管代码正在退出当前任务不得中止的时间段。</span><span class="sxs-lookup"><span data-stu-id="67ab0-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ab0-104">语法</span><span class="sxs-lookup"><span data-stu-id="67ab0-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="67ab0-105">返回值</span><span class="sxs-lookup"><span data-stu-id="67ab0-105">Return Value</span></span>  
  
|<span data-ttu-id="67ab0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67ab0-106">HRESULT</span></span>|<span data-ttu-id="67ab0-107">描述</span><span class="sxs-lookup"><span data-stu-id="67ab0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67ab0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="67ab0-108">S_OK</span></span>|<span data-ttu-id="67ab0-109">`EndDelayAbort` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="67ab0-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="67ab0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67ab0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67ab0-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="67ab0-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67ab0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67ab0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67ab0-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="67ab0-113">The call timed out.</span></span>|  
|<span data-ttu-id="67ab0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67ab0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67ab0-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="67ab0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67ab0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67ab0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67ab0-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="67ab0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67ab0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67ab0-118">E_FAIL</span></span>|<span data-ttu-id="67ab0-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="67ab0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67ab0-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="67ab0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67ab0-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="67ab0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67ab0-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="67ab0-122">E_UNEXPECTED</span></span>|<span data-ttu-id="67ab0-123">调用 `EndDelayAbort` 时未调用 `BeginDelayAbort`的相应调用。</span><span class="sxs-lookup"><span data-stu-id="67ab0-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67ab0-124">备注</span><span class="sxs-lookup"><span data-stu-id="67ab0-124">Remarks</span></span>  
 <span data-ttu-id="67ab0-125">在调用 `EndDelayAbort`之前，CLR 对当前任务的 `BeginDelayAbort` 进行相应的调用。</span><span class="sxs-lookup"><span data-stu-id="67ab0-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="67ab0-126">如果没有此类对应的调用，主机的[IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)实现应从 `EndDelayAbort`返回 E_UNEXPECTED，且不应采取任何措施。</span><span class="sxs-lookup"><span data-stu-id="67ab0-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67ab0-127">要求</span><span class="sxs-lookup"><span data-stu-id="67ab0-127">Requirements</span></span>  
 <span data-ttu-id="67ab0-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67ab0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67ab0-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67ab0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67ab0-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="67ab0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67ab0-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67ab0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ab0-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="67ab0-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="67ab0-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="67ab0-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="67ab0-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="67ab0-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="67ab0-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="67ab0-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="67ab0-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="67ab0-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
