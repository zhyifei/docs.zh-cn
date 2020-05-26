---
title: IHostGCManager::ThreadIsBlockingForSuspension 方法
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 0417a4acc0f4f39d8254eb5d5df3b3e690921a8a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804831"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="1a123-102">IHostGCManager::ThreadIsBlockingForSuspension 方法</span><span class="sxs-lookup"><span data-stu-id="1a123-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="1a123-103">通知宿主从中发出方法调用的线程将要阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="1a123-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a123-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a123-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1a123-105">返回值</span><span class="sxs-lookup"><span data-stu-id="1a123-105">Return Value</span></span>  
  
|<span data-ttu-id="1a123-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a123-106">HRESULT</span></span>|<span data-ttu-id="1a123-107">说明</span><span class="sxs-lookup"><span data-stu-id="1a123-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a123-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a123-108">S_OK</span></span>|<span data-ttu-id="1a123-109">`ThreadIsBlockingForSuspension`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1a123-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="1a123-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1a123-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1a123-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1a123-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1a123-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1a123-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1a123-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="1a123-113">The call timed out.</span></span>|  
|<span data-ttu-id="1a123-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1a123-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1a123-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1a123-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1a123-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1a123-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1a123-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="1a123-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1a123-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1a123-118">E_FAIL</span></span>|<span data-ttu-id="1a123-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1a123-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1a123-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="1a123-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1a123-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1a123-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a123-122">备注</span><span class="sxs-lookup"><span data-stu-id="1a123-122">Remarks</span></span>  
 <span data-ttu-id="1a123-123">CLR 通常会调用 `ThreadIsBlockForSuspension` 方法来准备垃圾回收，从而为主机提供重新计划线程以执行非托管任务的机会。</span><span class="sxs-lookup"><span data-stu-id="1a123-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a123-124">只有在调用之后，宿主才能重新安排任务 `ThreadIsBlockingForSuspension` 。</span><span class="sxs-lookup"><span data-stu-id="1a123-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="1a123-125">运行时调用[SuspensionStarting](ihostgcmanager-suspensionstarting-method.md)后，主机不得重新计划任务。</span><span class="sxs-lookup"><span data-stu-id="1a123-125">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a123-126">要求</span><span class="sxs-lookup"><span data-stu-id="1a123-126">Requirements</span></span>  
 <span data-ttu-id="1a123-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a123-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a123-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1a123-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a123-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1a123-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a123-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a123-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a123-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a123-131">See also</span></span>

- [<span data-ttu-id="1a123-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1a123-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1a123-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1a123-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1a123-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1a123-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1a123-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1a123-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="1a123-136">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="1a123-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
