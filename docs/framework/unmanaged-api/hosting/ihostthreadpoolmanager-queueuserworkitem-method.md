---
title: "IHostThreadPoolManager::QueueUserWorkItem 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.QueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0a304c2052192d3cba761a128e15dc463011030
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="018da-102">IHostThreadPoolManager::QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="018da-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="018da-103">排队的执行，函数，并指定包含数据以供该函数的对象。</span><span class="sxs-lookup"><span data-stu-id="018da-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="018da-104">在有线程变得可用时，将执行该函数。</span><span class="sxs-lookup"><span data-stu-id="018da-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="018da-105">语法</span><span class="sxs-lookup"><span data-stu-id="018da-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="018da-106">参数</span><span class="sxs-lookup"><span data-stu-id="018da-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="018da-107">[in]表示要执行的函数的函数指针。</span><span class="sxs-lookup"><span data-stu-id="018da-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="018da-108">[in]包含使用的数据的对象`Function`。</span><span class="sxs-lookup"><span data-stu-id="018da-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="018da-109">[in]其中一个标志的值，如定义为 Win32`QueueUserWorkItem`方法，以控制执行。</span><span class="sxs-lookup"><span data-stu-id="018da-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="018da-110">返回值</span><span class="sxs-lookup"><span data-stu-id="018da-110">Return Value</span></span>  
  
|<span data-ttu-id="018da-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="018da-111">HRESULT</span></span>|<span data-ttu-id="018da-112">描述</span><span class="sxs-lookup"><span data-stu-id="018da-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="018da-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="018da-113">S_OK</span></span>|<span data-ttu-id="018da-114">`QueueUserWorkItem`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="018da-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="018da-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="018da-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="018da-116">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="018da-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="018da-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="018da-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="018da-118">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="018da-118">The call timed out.</span></span>|  
|<span data-ttu-id="018da-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="018da-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="018da-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="018da-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="018da-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="018da-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="018da-122">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="018da-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="018da-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="018da-123">E_FAIL</span></span>|<span data-ttu-id="018da-124">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="018da-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="018da-125">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="018da-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="018da-126">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="018da-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="018da-127">备注</span><span class="sxs-lookup"><span data-stu-id="018da-127">Remarks</span></span>  
 <span data-ttu-id="018da-128">`QueueUserWorkItem`排队到线程池的工作线程的工作项。</span><span class="sxs-lookup"><span data-stu-id="018da-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="018da-129">其签名和参数类型是相应的 Win32 函数具有相同的名称相同。</span><span class="sxs-lookup"><span data-stu-id="018da-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="018da-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="018da-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="018da-131">惠?</span><span class="sxs-lookup"><span data-stu-id="018da-131">Requirements</span></span>  
 <span data-ttu-id="018da-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="018da-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="018da-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="018da-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="018da-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="018da-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="018da-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="018da-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018da-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="018da-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="018da-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="018da-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
