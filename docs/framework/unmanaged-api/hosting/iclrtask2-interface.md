---
title: ICLRTask2 接口
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cbd627eff9318fce38ec238e5fa686cc9d759b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627182"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="b65e0-102">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="b65e0-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="b65e0-103">提供的所有功能[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口; 此外，还都提供允许线程中止当前线程上延迟的方法。</span><span class="sxs-lookup"><span data-stu-id="b65e0-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b65e0-104">方法</span><span class="sxs-lookup"><span data-stu-id="b65e0-104">Methods</span></span>  
  
|<span data-ttu-id="b65e0-105">方法</span><span class="sxs-lookup"><span data-stu-id="b65e0-105">Method</span></span>|<span data-ttu-id="b65e0-106">描述</span><span class="sxs-lookup"><span data-stu-id="b65e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b65e0-107">BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="b65e0-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="b65e0-108">延迟的新线程中止当前线程上的请求。</span><span class="sxs-lookup"><span data-stu-id="b65e0-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="b65e0-109">EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="b65e0-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="b65e0-110">允许新的或挂起的线程中止请求导致线程中止当前线程上。</span><span class="sxs-lookup"><span data-stu-id="b65e0-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b65e0-111">备注</span><span class="sxs-lookup"><span data-stu-id="b65e0-111">Remarks</span></span>  
 <span data-ttu-id="b65e0-112">`ICLRTask2`接口继承自`ICLRTask`接口，并添加方法，以使宿主延迟线程中止，若要保护的代码必须不发生故障的区域。</span><span class="sxs-lookup"><span data-stu-id="b65e0-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="b65e0-113">调用`BeginPreventAsyncAbort`递增的当前线程和调用的延迟线程中止计数器`EndPreventAsyncAbort`递减它。</span><span class="sxs-lookup"><span data-stu-id="b65e0-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="b65e0-114">调用`BeginPreventAsyncAbort`和`EndPreventAsyncAbort`可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="b65e0-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="b65e0-115">只要该计数器是大于零，则会延迟当前线程的线程中止。</span><span class="sxs-lookup"><span data-stu-id="b65e0-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="b65e0-116">如果调用`BeginPreventAsyncAbort`和`EndPreventAsyncAbort`不是成对，则可能会进入在哪个线程中止不能传递到当前线程的状态。</span><span class="sxs-lookup"><span data-stu-id="b65e0-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="b65e0-117">不为线程中止本身采用延迟。</span><span class="sxs-lookup"><span data-stu-id="b65e0-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="b65e0-118">虚拟机 (VM) 在内部使用此功能公开的功能。</span><span class="sxs-lookup"><span data-stu-id="b65e0-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="b65e0-119">不恰当使用这些方法的可能导致在 VM 中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="b65e0-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="b65e0-120">例如，调用`EndPreventAsyncAbort`而无需第一个调用`BeginPreventAsyncAbort`VM 先前已增大时，无法设置计数器为零。</span><span class="sxs-lookup"><span data-stu-id="b65e0-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="b65e0-121">同样，内部计数器不会检查溢出。</span><span class="sxs-lookup"><span data-stu-id="b65e0-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="b65e0-122">如果因为加在主机和 VM 超出其不可或缺的限制，所产生的行为是未指定。</span><span class="sxs-lookup"><span data-stu-id="b65e0-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="b65e0-123">为继承其成员的信息`ICLRTask`和此接口的其他用法，请参阅[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b65e0-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b65e0-124">要求</span><span class="sxs-lookup"><span data-stu-id="b65e0-124">Requirements</span></span>  
 <span data-ttu-id="b65e0-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b65e0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b65e0-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b65e0-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b65e0-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b65e0-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b65e0-128">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65e0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65e0-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b65e0-129">See also</span></span>
- [<span data-ttu-id="b65e0-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="b65e0-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b65e0-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b65e0-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b65e0-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="b65e0-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b65e0-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b65e0-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="b65e0-134">承载接口</span><span class="sxs-lookup"><span data-stu-id="b65e0-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
