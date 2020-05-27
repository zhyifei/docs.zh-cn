---
title: IHostTaskManager::EndThreadAffinity 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: 2e857f951a837e1385d02dfc810fc12cfefd0d2b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841953"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="169aa-102">IHostTaskManager::EndThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="169aa-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="169aa-103">在之前调用[IHostTaskManager：： BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md)时，通知宿主托管代码正在退出不能将当前任务移动到另一个操作系统线程的时间段。</span><span class="sxs-lookup"><span data-stu-id="169aa-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="169aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="169aa-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="169aa-105">返回值</span><span class="sxs-lookup"><span data-stu-id="169aa-105">Return Value</span></span>  
  
|<span data-ttu-id="169aa-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="169aa-106">HRESULT</span></span>|<span data-ttu-id="169aa-107">说明</span><span class="sxs-lookup"><span data-stu-id="169aa-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="169aa-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="169aa-108">S_OK</span></span>|<span data-ttu-id="169aa-109">`EndThreadAffinity`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="169aa-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="169aa-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="169aa-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="169aa-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="169aa-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="169aa-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="169aa-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="169aa-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="169aa-113">The call timed out.</span></span>|  
|<span data-ttu-id="169aa-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="169aa-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="169aa-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="169aa-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="169aa-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="169aa-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="169aa-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="169aa-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="169aa-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="169aa-118">E_FAIL</span></span>|<span data-ttu-id="169aa-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="169aa-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="169aa-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="169aa-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="169aa-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="169aa-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="169aa-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="169aa-122">E_UNEXPECTED</span></span>|<span data-ttu-id="169aa-123">`EndThreadAffinity`在没有对的早期调用的情况下调用 `BeginThreadAffinity` 。</span><span class="sxs-lookup"><span data-stu-id="169aa-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="169aa-124">备注</span><span class="sxs-lookup"><span data-stu-id="169aa-124">Remarks</span></span>  
 <span data-ttu-id="169aa-125">在调用之前，CLR 对当前任务进行相应的调用 `BeginThreadAffinity` `EndThreadAffinity` 。</span><span class="sxs-lookup"><span data-stu-id="169aa-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="169aa-126">如果没有此类对应的调用，主机的[IHostTaskManager](ihosttaskmanager-interface.md)实现应返回 E_UNEXPECTED，而不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="169aa-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="169aa-127">要求</span><span class="sxs-lookup"><span data-stu-id="169aa-127">Requirements</span></span>  
 <span data-ttu-id="169aa-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="169aa-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="169aa-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="169aa-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="169aa-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="169aa-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="169aa-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="169aa-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169aa-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="169aa-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="169aa-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="169aa-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="169aa-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="169aa-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="169aa-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="169aa-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="169aa-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="169aa-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
