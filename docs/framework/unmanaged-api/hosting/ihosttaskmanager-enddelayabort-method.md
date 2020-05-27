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
ms.openlocfilehash: 156626ce907c13987c0cca15016263291961037d
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841966"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="d46e3-102">IHostTaskManager::EndDelayAbort 方法</span><span class="sxs-lookup"><span data-stu-id="d46e3-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="d46e3-103">在之前调用[IHostTaskManager：： BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md)时，通知宿主托管代码正在退出当前任务不得中止的时间段。</span><span class="sxs-lookup"><span data-stu-id="d46e3-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d46e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d46e3-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d46e3-105">返回值</span><span class="sxs-lookup"><span data-stu-id="d46e3-105">Return Value</span></span>  
  
|<span data-ttu-id="d46e3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d46e3-106">HRESULT</span></span>|<span data-ttu-id="d46e3-107">说明</span><span class="sxs-lookup"><span data-stu-id="d46e3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d46e3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d46e3-108">S_OK</span></span>|<span data-ttu-id="d46e3-109">`EndDelayAbort`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d46e3-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="d46e3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d46e3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d46e3-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d46e3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d46e3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d46e3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d46e3-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d46e3-113">The call timed out.</span></span>|  
|<span data-ttu-id="d46e3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d46e3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d46e3-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d46e3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d46e3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d46e3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d46e3-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d46e3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d46e3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d46e3-118">E_FAIL</span></span>|<span data-ttu-id="d46e3-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d46e3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d46e3-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d46e3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d46e3-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d46e3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d46e3-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="d46e3-122">E_UNEXPECTED</span></span>|<span data-ttu-id="d46e3-123">`EndDelayAbort`在未调用的情况下调用 `BeginDelayAbort` 。</span><span class="sxs-lookup"><span data-stu-id="d46e3-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d46e3-124">备注</span><span class="sxs-lookup"><span data-stu-id="d46e3-124">Remarks</span></span>  
 <span data-ttu-id="d46e3-125">在调用之前，CLR 对当前任务进行相应的调用 `BeginDelayAbort` `EndDelayAbort` 。</span><span class="sxs-lookup"><span data-stu-id="d46e3-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="d46e3-126">如果没有此类对应的调用，主机的[IHostTaskManager](ihosttaskmanager-interface.md)实现应从返回 E_UNEXPECTED `EndDelayAbort` ，而不应采取任何措施。</span><span class="sxs-lookup"><span data-stu-id="d46e3-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d46e3-127">要求</span><span class="sxs-lookup"><span data-stu-id="d46e3-127">Requirements</span></span>  
 <span data-ttu-id="d46e3-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d46e3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d46e3-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d46e3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d46e3-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d46e3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d46e3-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d46e3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d46e3-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d46e3-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="d46e3-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d46e3-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="d46e3-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d46e3-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="d46e3-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d46e3-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="d46e3-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d46e3-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
