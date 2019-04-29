---
title: IHostThreadPoolManager::QueueUserWorkItem 方法
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c548ae7f8d605ff84da2046d057e436c8e95721
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796558"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="8353b-102">IHostThreadPoolManager::QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="8353b-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="8353b-103">队列的函数的执行，并指定一个包含该函数使用的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="8353b-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="8353b-104">该函数执行时在线程变得可用。</span><span class="sxs-lookup"><span data-stu-id="8353b-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8353b-105">语法</span><span class="sxs-lookup"><span data-stu-id="8353b-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8353b-106">参数</span><span class="sxs-lookup"><span data-stu-id="8353b-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="8353b-107">[in]表示要执行的函数的函数指针。</span><span class="sxs-lookup"><span data-stu-id="8353b-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="8353b-108">[in]一个对象，包含要在通过数据`Function`。</span><span class="sxs-lookup"><span data-stu-id="8353b-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="8353b-109">[in]标志值之一，定义为 Win32`QueueUserWorkItem`方法，用于控制执行。</span><span class="sxs-lookup"><span data-stu-id="8353b-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8353b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8353b-110">Return Value</span></span>  
  
|<span data-ttu-id="8353b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8353b-111">HRESULT</span></span>|<span data-ttu-id="8353b-112">描述</span><span class="sxs-lookup"><span data-stu-id="8353b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8353b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8353b-113">S_OK</span></span>|<span data-ttu-id="8353b-114">`QueueUserWorkItem` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8353b-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="8353b-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8353b-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8353b-116">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8353b-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8353b-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8353b-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8353b-118">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="8353b-118">The call timed out.</span></span>|  
|<span data-ttu-id="8353b-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8353b-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8353b-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8353b-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8353b-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8353b-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8353b-122">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8353b-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8353b-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8353b-123">E_FAIL</span></span>|<span data-ttu-id="8353b-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8353b-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8353b-125">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="8353b-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8353b-126">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8353b-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8353b-127">备注</span><span class="sxs-lookup"><span data-stu-id="8353b-127">Remarks</span></span>  
 <span data-ttu-id="8353b-128">`QueueUserWorkItem` 到线程池的工作线程的工作项进行排队。</span><span class="sxs-lookup"><span data-stu-id="8353b-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="8353b-129">其签名和参数类型是与相应的 Win32 函数具有相同的名称相同。</span><span class="sxs-lookup"><span data-stu-id="8353b-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="8353b-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="8353b-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8353b-131">要求</span><span class="sxs-lookup"><span data-stu-id="8353b-131">Requirements</span></span>  
 <span data-ttu-id="8353b-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8353b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8353b-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8353b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8353b-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8353b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8353b-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8353b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8353b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8353b-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="8353b-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="8353b-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
