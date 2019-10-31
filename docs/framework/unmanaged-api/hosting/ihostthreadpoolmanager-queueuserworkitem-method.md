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
ms.openlocfilehash: 39c35884d0fb53baefafbf86391a349e141418a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141323"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="ffbbd-102">IHostThreadPoolManager::QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="ffbbd-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="ffbbd-103">将函数排队以便执行，并指定包含该函数要使用的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="ffbbd-104">当线程变为可用时，该函数执行。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffbbd-105">语法</span><span class="sxs-lookup"><span data-stu-id="ffbbd-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffbbd-106">参数</span><span class="sxs-lookup"><span data-stu-id="ffbbd-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="ffbbd-107">中表示要执行的函数的函数指针。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="ffbbd-108">中一个对象，包含 `Function`要使用的数据。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="ffbbd-109">中为 Win32 `QueueUserWorkItem` 方法定义的、用于控制执行的标志值之一。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffbbd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ffbbd-110">Return Value</span></span>  
  
|<span data-ttu-id="ffbbd-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffbbd-111">HRESULT</span></span>|<span data-ttu-id="ffbbd-112">描述</span><span class="sxs-lookup"><span data-stu-id="ffbbd-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffbbd-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffbbd-113">S_OK</span></span>|<span data-ttu-id="ffbbd-114">`QueueUserWorkItem` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="ffbbd-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffbbd-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffbbd-116">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffbbd-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffbbd-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffbbd-118">调用超时。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-118">The call timed out.</span></span>|  
|<span data-ttu-id="ffbbd-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffbbd-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffbbd-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffbbd-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffbbd-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffbbd-122">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffbbd-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffbbd-123">E_FAIL</span></span>|<span data-ttu-id="ffbbd-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffbbd-125">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffbbd-126">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffbbd-127">备注</span><span class="sxs-lookup"><span data-stu-id="ffbbd-127">Remarks</span></span>  
 <span data-ttu-id="ffbbd-128">`QueueUserWorkItem` 将工作项排队到线程池中的工作线程。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="ffbbd-129">其签名和参数类型与具有相同名称的对应 Win32 函数的签名和参数类型相同。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="ffbbd-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffbbd-131">要求</span><span class="sxs-lookup"><span data-stu-id="ffbbd-131">Requirements</span></span>  
 <span data-ttu-id="ffbbd-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffbbd-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffbbd-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ffbbd-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffbbd-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ffbbd-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffbbd-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffbbd-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbbd-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffbbd-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ffbbd-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="ffbbd-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
