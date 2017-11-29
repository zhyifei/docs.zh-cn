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
ms.openlocfilehash: 9948673d6988de21c83c37538fb4d7c030296e58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="58c49-102">IHostThreadPoolManager::QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="58c49-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="58c49-103">排队的执行，函数，并指定包含数据以供该函数的对象。</span><span class="sxs-lookup"><span data-stu-id="58c49-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="58c49-104">在有线程变得可用时，将执行该函数。</span><span class="sxs-lookup"><span data-stu-id="58c49-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c49-105">语法</span><span class="sxs-lookup"><span data-stu-id="58c49-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58c49-106">参数</span><span class="sxs-lookup"><span data-stu-id="58c49-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="58c49-107">[in]表示要执行的函数的函数指针。</span><span class="sxs-lookup"><span data-stu-id="58c49-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="58c49-108">[in]包含使用的数据的对象`Function`。</span><span class="sxs-lookup"><span data-stu-id="58c49-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="58c49-109">[in]其中一个标志的值，如定义为 Win32`QueueUserWorkItem`方法，以控制执行。</span><span class="sxs-lookup"><span data-stu-id="58c49-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58c49-110">返回值</span><span class="sxs-lookup"><span data-stu-id="58c49-110">Return Value</span></span>  
  
|<span data-ttu-id="58c49-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58c49-111">HRESULT</span></span>|<span data-ttu-id="58c49-112">描述</span><span class="sxs-lookup"><span data-stu-id="58c49-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58c49-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="58c49-113">S_OK</span></span>|<span data-ttu-id="58c49-114">`QueueUserWorkItem`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="58c49-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="58c49-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58c49-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58c49-116">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="58c49-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58c49-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58c49-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58c49-118">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="58c49-118">The call timed out.</span></span>|  
|<span data-ttu-id="58c49-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58c49-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58c49-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="58c49-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58c49-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58c49-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58c49-122">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="58c49-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58c49-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58c49-123">E_FAIL</span></span>|<span data-ttu-id="58c49-124">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="58c49-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58c49-125">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="58c49-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58c49-126">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="58c49-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58c49-127">备注</span><span class="sxs-lookup"><span data-stu-id="58c49-127">Remarks</span></span>  
 <span data-ttu-id="58c49-128">`QueueUserWorkItem`排队到线程池的工作线程的工作项。</span><span class="sxs-lookup"><span data-stu-id="58c49-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="58c49-129">其签名和参数类型是相应的 Win32 函数具有相同的名称相同。</span><span class="sxs-lookup"><span data-stu-id="58c49-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="58c49-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="58c49-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c49-131">要求</span><span class="sxs-lookup"><span data-stu-id="58c49-131">Requirements</span></span>  
 <span data-ttu-id="58c49-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58c49-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c49-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58c49-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58c49-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58c49-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58c49-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c49-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c49-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58c49-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="58c49-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="58c49-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
