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
ms.openlocfilehash: 5e1b5c0f5636748b96cc7d9667155581f1595a4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438400"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="dcdb7-102">ICLRTask2::BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="dcdb7-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="dcdb7-103">延迟新线程中止从导致当前线程上的线程中止的请求。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcdb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="dcdb7-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dcdb7-105">返回值</span><span class="sxs-lookup"><span data-stu-id="dcdb7-105">Return Value</span></span>  
 <span data-ttu-id="dcdb7-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dcdb7-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dcdb7-107">HRESULT</span></span>|<span data-ttu-id="dcdb7-108">描述</span><span class="sxs-lookup"><span data-stu-id="dcdb7-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dcdb7-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="dcdb7-109">S_OK</span></span>|<span data-ttu-id="dcdb7-110">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="dcdb7-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="dcdb7-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="dcdb7-112">这不是当前线程的线程上调用了方法。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcdb7-113">备注</span><span class="sxs-lookup"><span data-stu-id="dcdb7-113">Remarks</span></span>  
 <span data-ttu-id="dcdb7-114">调用此方法通过一个递增当前线程的延迟线程中止计数器。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="dcdb7-115">调用`BeginPreventAsyncAbort`和[iclrtask2:: Endpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="dcdb7-116">只要计数器值大于零，当前线程的线程中止延迟。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="dcdb7-117">如果此调用未配对通过调用`EndPreventAsyncAbort`方法，它是可能会进入在哪个线程中止无法传送到当前线程的状态。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="dcdb7-118">延迟将不接受中止本身一个线程。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="dcdb7-119">虚拟机 (VM) 内部使用此功能公开的功能。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="dcdb7-120">不正确使用了这些方法可能导致虚拟机中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="dcdb7-121">例如，调用`EndPreventAsyncAbort`而无需首先调用`BeginPreventAsyncAbort`VM 先前已增大时无法设置为零的计数器。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="dcdb7-122">同样，内部计数器未检查存在溢出。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="dcdb7-123">如果该阈值超过其整型的限制，因为它就会递增主机和 VM，获得的行为是未指定。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcdb7-124">要求</span><span class="sxs-lookup"><span data-stu-id="dcdb7-124">Requirements</span></span>  
 <span data-ttu-id="dcdb7-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dcdb7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcdb7-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dcdb7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dcdb7-127">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dcdb7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcdb7-128">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcdb7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcdb7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcdb7-129">See Also</span></span>  
 [<span data-ttu-id="dcdb7-130">EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="dcdb7-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)  
 [<span data-ttu-id="dcdb7-131">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="dcdb7-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="dcdb7-132">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="dcdb7-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="dcdb7-133">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="dcdb7-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="dcdb7-134">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="dcdb7-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="dcdb7-135">承载接口</span><span class="sxs-lookup"><span data-stu-id="dcdb7-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
