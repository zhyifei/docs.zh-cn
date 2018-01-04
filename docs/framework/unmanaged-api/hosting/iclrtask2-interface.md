---
title: "ICLRTask2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8701cff3400e46660fac90486cf5648d29aa9972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="cfaac-102">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="cfaac-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="cfaac-103">提供的所有功能[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口; 此外，提供都了允许线程中止延迟，可将当前线程上的方法。</span><span class="sxs-lookup"><span data-stu-id="cfaac-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfaac-104">方法</span><span class="sxs-lookup"><span data-stu-id="cfaac-104">Methods</span></span>  
  
|<span data-ttu-id="cfaac-105">方法</span><span class="sxs-lookup"><span data-stu-id="cfaac-105">Method</span></span>|<span data-ttu-id="cfaac-106">描述</span><span class="sxs-lookup"><span data-stu-id="cfaac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfaac-107">BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="cfaac-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="cfaac-108">延迟新线程中止当前线程上的请求。</span><span class="sxs-lookup"><span data-stu-id="cfaac-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="cfaac-109">EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="cfaac-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="cfaac-110">允许新的或挂起的线程中止请求导致线程中止当前线程上。</span><span class="sxs-lookup"><span data-stu-id="cfaac-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfaac-111">备注</span><span class="sxs-lookup"><span data-stu-id="cfaac-111">Remarks</span></span>  
 <span data-ttu-id="cfaac-112">`ICLRTask2`接口继承`ICLRTask`接口，并添加允许主机延迟线程中止，以防一定不能失败的代码区域的方法。</span><span class="sxs-lookup"><span data-stu-id="cfaac-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="cfaac-113">调用`BeginPreventAsyncAbort`递增的当前线程和调用的延迟线程中止计数器`EndPreventAsyncAbort`递减它。</span><span class="sxs-lookup"><span data-stu-id="cfaac-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="cfaac-114">调用`BeginPreventAsyncAbort`和`EndPreventAsyncAbort`可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="cfaac-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="cfaac-115">只要计数器值大于零，当前线程的线程中止延迟。</span><span class="sxs-lookup"><span data-stu-id="cfaac-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="cfaac-116">如果调用`BeginPreventAsyncAbort`和`EndPreventAsyncAbort`不是成对，则可能会进入在哪个线程中止无法传送到当前线程的状态。</span><span class="sxs-lookup"><span data-stu-id="cfaac-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="cfaac-117">延迟将不接受中止本身一个线程。</span><span class="sxs-lookup"><span data-stu-id="cfaac-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="cfaac-118">虚拟机 (VM) 内部使用此功能公开的功能。</span><span class="sxs-lookup"><span data-stu-id="cfaac-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="cfaac-119">不正确使用了这些方法可能导致虚拟机中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="cfaac-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="cfaac-120">例如，调用`EndPreventAsyncAbort`而无需首先调用`BeginPreventAsyncAbort`VM 先前已增大时无法设置为零的计数器。</span><span class="sxs-lookup"><span data-stu-id="cfaac-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="cfaac-121">同样，内部计数器未检查存在溢出。</span><span class="sxs-lookup"><span data-stu-id="cfaac-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="cfaac-122">如果该阈值超过其整型的限制，因为它就会递增主机和 VM，获得的行为是未指定。</span><span class="sxs-lookup"><span data-stu-id="cfaac-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="cfaac-123">有关成员的信息从继承为`ICLRTask`和此接口的其他用法，请参阅[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="cfaac-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfaac-124">惠?</span><span class="sxs-lookup"><span data-stu-id="cfaac-124">Requirements</span></span>  
 <span data-ttu-id="cfaac-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfaac-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfaac-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cfaac-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfaac-127">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cfaac-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfaac-128">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfaac-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfaac-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfaac-129">See Also</span></span>  
 [<span data-ttu-id="cfaac-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="cfaac-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="cfaac-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="cfaac-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="cfaac-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="cfaac-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="cfaac-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="cfaac-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="cfaac-134">承载接口</span><span class="sxs-lookup"><span data-stu-id="cfaac-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
