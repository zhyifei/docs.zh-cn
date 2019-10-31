---
title: ICLRTask2::BeginPreventAsyncAbort 方法
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 67841bbcd796e41b3b81f922020fe6c3677730c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124565"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="8f45f-102">ICLRTask2::BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="8f45f-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="8f45f-103">使新线程中止请求延迟，导致线程在当前线程上中止。</span><span class="sxs-lookup"><span data-stu-id="8f45f-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f45f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f45f-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8f45f-105">返回值</span><span class="sxs-lookup"><span data-stu-id="8f45f-105">Return Value</span></span>  
 <span data-ttu-id="8f45f-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="8f45f-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8f45f-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f45f-107">HRESULT</span></span>|<span data-ttu-id="8f45f-108">描述</span><span class="sxs-lookup"><span data-stu-id="8f45f-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f45f-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f45f-109">S_OK</span></span>|<span data-ttu-id="8f45f-110">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8f45f-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="8f45f-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8f45f-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8f45f-112">在不是当前线程的线程上调用了方法。</span><span class="sxs-lookup"><span data-stu-id="8f45f-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f45f-113">备注</span><span class="sxs-lookup"><span data-stu-id="8f45f-113">Remarks</span></span>  
 <span data-ttu-id="8f45f-114">调用此方法会将当前线程的延迟线程中止计数器增加一个。</span><span class="sxs-lookup"><span data-stu-id="8f45f-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="8f45f-115">可以嵌套对 `BeginPreventAsyncAbort` 和[ICLRTask2：： EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)的调用。</span><span class="sxs-lookup"><span data-stu-id="8f45f-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="8f45f-116">只要计数器大于零，就会延迟当前线程的线程中止。</span><span class="sxs-lookup"><span data-stu-id="8f45f-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="8f45f-117">如果此调用与对 `EndPreventAsyncAbort` 方法的调用不成对，则可能会达到无法将线程中止传递到当前线程的状态。</span><span class="sxs-lookup"><span data-stu-id="8f45f-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="8f45f-118">此延迟不适用于自行中止的线程。</span><span class="sxs-lookup"><span data-stu-id="8f45f-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="8f45f-119">此功能公开的功能由虚拟机（VM）在内部使用。</span><span class="sxs-lookup"><span data-stu-id="8f45f-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="8f45f-120">滥用这些方法可能会导致 VM 中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="8f45f-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="8f45f-121">例如，如果不首先调用 `BeginPreventAsyncAbort` 调用 `EndPreventAsyncAbort` 可以将计数器设置为零。</span><span class="sxs-lookup"><span data-stu-id="8f45f-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="8f45f-122">同样，不检查内部计数器是否溢出。</span><span class="sxs-lookup"><span data-stu-id="8f45f-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="8f45f-123">如果它超过其整数限制，原因是主机和 VM 均递增，则未指定产生的行为。</span><span class="sxs-lookup"><span data-stu-id="8f45f-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f45f-124">要求</span><span class="sxs-lookup"><span data-stu-id="8f45f-124">Requirements</span></span>  
 <span data-ttu-id="8f45f-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f45f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f45f-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f45f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f45f-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8f45f-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f45f-128">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f45f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f45f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f45f-129">See also</span></span>

- [<span data-ttu-id="8f45f-130">EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="8f45f-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="8f45f-131">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="8f45f-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="8f45f-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8f45f-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8f45f-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="8f45f-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8f45f-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="8f45f-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="8f45f-135">承载接口</span><span class="sxs-lookup"><span data-stu-id="8f45f-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
