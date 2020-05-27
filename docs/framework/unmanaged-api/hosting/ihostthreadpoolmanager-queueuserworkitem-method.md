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
ms.openlocfilehash: b3d77e30cd48310c392d38dc29f62fab565c8b42
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842460"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="9641b-102">IHostThreadPoolManager::QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="9641b-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="9641b-103">将函数排队以便执行，并指定包含该函数要使用的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="9641b-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="9641b-104">当线程变为可用时，该函数执行。</span><span class="sxs-lookup"><span data-stu-id="9641b-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9641b-105">语法</span><span class="sxs-lookup"><span data-stu-id="9641b-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9641b-106">参数</span><span class="sxs-lookup"><span data-stu-id="9641b-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="9641b-107">中表示要执行的函数的函数指针。</span><span class="sxs-lookup"><span data-stu-id="9641b-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="9641b-108">中包含要使用的数据的对象 `Function` 。</span><span class="sxs-lookup"><span data-stu-id="9641b-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="9641b-109">中用于控制执行的、针对 Win32 方法定义的标志值之一 `QueueUserWorkItem` 。</span><span class="sxs-lookup"><span data-stu-id="9641b-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9641b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9641b-110">Return Value</span></span>  
  
|<span data-ttu-id="9641b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9641b-111">HRESULT</span></span>|<span data-ttu-id="9641b-112">说明</span><span class="sxs-lookup"><span data-stu-id="9641b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9641b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9641b-113">S_OK</span></span>|<span data-ttu-id="9641b-114">`QueueUserWorkItem`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9641b-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="9641b-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9641b-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9641b-116">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9641b-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9641b-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9641b-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9641b-118">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9641b-118">The call timed out.</span></span>|  
|<span data-ttu-id="9641b-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9641b-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9641b-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9641b-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9641b-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9641b-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9641b-122">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9641b-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9641b-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9641b-123">E_FAIL</span></span>|<span data-ttu-id="9641b-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9641b-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9641b-125">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9641b-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9641b-126">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9641b-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9641b-127">备注</span><span class="sxs-lookup"><span data-stu-id="9641b-127">Remarks</span></span>  
 <span data-ttu-id="9641b-128">`QueueUserWorkItem`将工作项排队到线程池中的工作线程。</span><span class="sxs-lookup"><span data-stu-id="9641b-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="9641b-129">其签名和参数类型与具有相同名称的对应 Win32 函数的签名和参数类型相同。</span><span class="sxs-lookup"><span data-stu-id="9641b-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="9641b-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="9641b-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9641b-131">要求</span><span class="sxs-lookup"><span data-stu-id="9641b-131">Requirements</span></span>  
 <span data-ttu-id="9641b-132">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9641b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9641b-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9641b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9641b-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9641b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9641b-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9641b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9641b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9641b-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="9641b-137">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="9641b-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
