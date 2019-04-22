---
title: ICLRTask2::EndPreventAsyncAbort 方法
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60997717baf70e10366e7f0ba6a06daa1f35f8cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121662"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="a5109-102">ICLRTask2::EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="a5109-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="a5109-103">允许新的或挂起的线程中止请求导致线程中止当前线程上。</span><span class="sxs-lookup"><span data-stu-id="a5109-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5109-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5109-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a5109-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a5109-105">Return Value</span></span>  
 <span data-ttu-id="a5109-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a5109-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a5109-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5109-107">HRESULT</span></span>|<span data-ttu-id="a5109-108">描述</span><span class="sxs-lookup"><span data-stu-id="a5109-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5109-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5109-109">S_OK</span></span>|<span data-ttu-id="a5109-110">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="a5109-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="a5109-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a5109-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a5109-112">这不是当前线程的线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="a5109-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5109-113">备注</span><span class="sxs-lookup"><span data-stu-id="a5109-113">Remarks</span></span>  
 <span data-ttu-id="a5109-114">调用此方法减少延迟线程中止计数器为当前线程的一个。</span><span class="sxs-lookup"><span data-stu-id="a5109-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="a5109-115">调用[ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)和`EndPreventAsyncAbort`可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="a5109-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="a5109-116">只要该计数器是大于零，则会延迟当前线程的线程中止。</span><span class="sxs-lookup"><span data-stu-id="a5109-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="a5109-117">虚拟机 (VM) 在内部使用此功能公开的功能。</span><span class="sxs-lookup"><span data-stu-id="a5109-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="a5109-118">不恰当使用这些方法的可能导致在 VM 中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="a5109-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="a5109-119">例如，调用`EndPreventAsyncAbort`而无需第一个调用`BeginPreventAsyncAbort`VM 先前已增大时，无法设置计数器为零。</span><span class="sxs-lookup"><span data-stu-id="a5109-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="a5109-120">同样，内部计数器不会检查溢出。</span><span class="sxs-lookup"><span data-stu-id="a5109-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="a5109-121">如果因为加在主机和 VM 超出其不可或缺的限制，所产生的行为是未指定。</span><span class="sxs-lookup"><span data-stu-id="a5109-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5109-122">要求</span><span class="sxs-lookup"><span data-stu-id="a5109-122">Requirements</span></span>  
 <span data-ttu-id="a5109-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5109-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5109-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a5109-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5109-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a5109-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5109-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5109-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5109-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5109-127">See also</span></span>

- [<span data-ttu-id="a5109-128">BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="a5109-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="a5109-129">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="a5109-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="a5109-130">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a5109-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a5109-131">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a5109-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a5109-132">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a5109-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="a5109-133">承载接口</span><span class="sxs-lookup"><span data-stu-id="a5109-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
