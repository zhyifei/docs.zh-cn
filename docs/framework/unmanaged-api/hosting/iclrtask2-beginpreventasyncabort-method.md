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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a43fef7f6dfa6dbe0bb9f1c4caec2c9c224b93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213579"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="ed821-102">ICLRTask2::BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="ed821-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="ed821-103">延迟新线程中止请求导致当前线程上的线程中止。</span><span class="sxs-lookup"><span data-stu-id="ed821-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed821-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed821-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ed821-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ed821-105">Return Value</span></span>  
 <span data-ttu-id="ed821-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ed821-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ed821-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed821-107">HRESULT</span></span>|<span data-ttu-id="ed821-108">描述</span><span class="sxs-lookup"><span data-stu-id="ed821-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed821-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed821-109">S_OK</span></span>|<span data-ttu-id="ed821-110">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ed821-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="ed821-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ed821-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ed821-112">这不是当前线程的线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="ed821-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed821-113">备注</span><span class="sxs-lookup"><span data-stu-id="ed821-113">Remarks</span></span>  
 <span data-ttu-id="ed821-114">调用此方法由一个递增当前线程的延迟线程中止计数器。</span><span class="sxs-lookup"><span data-stu-id="ed821-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="ed821-115">调用`BeginPreventAsyncAbort`并[ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="ed821-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="ed821-116">只要该计数器是大于零，则会延迟当前线程的线程中止。</span><span class="sxs-lookup"><span data-stu-id="ed821-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="ed821-117">如果此调用未配对通过调用`EndPreventAsyncAbort`方法，就可以访问哪些线程中止不能将传递到当前线程的状态。</span><span class="sxs-lookup"><span data-stu-id="ed821-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="ed821-118">不为线程中止本身采用延迟。</span><span class="sxs-lookup"><span data-stu-id="ed821-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="ed821-119">虚拟机 (VM) 在内部使用此功能公开的功能。</span><span class="sxs-lookup"><span data-stu-id="ed821-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="ed821-120">不恰当使用这些方法的可能导致在 VM 中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="ed821-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="ed821-121">例如，调用`EndPreventAsyncAbort`而无需第一个调用`BeginPreventAsyncAbort`VM 先前已增大时，无法设置计数器为零。</span><span class="sxs-lookup"><span data-stu-id="ed821-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="ed821-122">同样，内部计数器不会检查溢出。</span><span class="sxs-lookup"><span data-stu-id="ed821-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="ed821-123">如果因为加在主机和 VM 超出其不可或缺的限制，所产生的行为是未指定。</span><span class="sxs-lookup"><span data-stu-id="ed821-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed821-124">要求</span><span class="sxs-lookup"><span data-stu-id="ed821-124">Requirements</span></span>  
 <span data-ttu-id="ed821-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed821-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed821-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed821-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed821-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ed821-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ed821-128">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ed821-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed821-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed821-129">See also</span></span>

- [<span data-ttu-id="ed821-130">EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="ed821-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="ed821-131">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="ed821-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="ed821-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ed821-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ed821-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="ed821-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ed821-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ed821-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ed821-135">承载接口</span><span class="sxs-lookup"><span data-stu-id="ed821-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
