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
ms.openlocfilehash: 3ea36c56ef9ccf5886ba96191627e5283da186f7
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762847"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="a4c4b-102">ICLRTask2::EndPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="a4c4b-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="a4c4b-103">允许新的或挂起的线程中止请求导致在当前线程上中止线程。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4c4b-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a4c4b-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a4c4b-105">Return Value</span></span>  
 <span data-ttu-id="a4c4b-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a4c4b-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4c4b-107">HRESULT</span></span>|<span data-ttu-id="a4c4b-108">说明</span><span class="sxs-lookup"><span data-stu-id="a4c4b-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4c4b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4c4b-109">S_OK</span></span>|<span data-ttu-id="a4c4b-110">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="a4c4b-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a4c4b-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a4c4b-112">在不是当前线程的线程上调用了方法。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4c4b-113">注解</span><span class="sxs-lookup"><span data-stu-id="a4c4b-113">Remarks</span></span>  
 <span data-ttu-id="a4c4b-114">调用此方法会将当前线程的延迟线程中止计数器减一。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="a4c4b-115">调用[ICLRTask2：： BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) ， `EndPreventAsyncAbort` 可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="a4c4b-116">只要计数器大于零，就会延迟当前线程的线程中止。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="a4c4b-117">此功能公开的功能由虚拟机（VM）在内部使用。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="a4c4b-118">滥用这些方法可能会导致 VM 中未指定的行为。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="a4c4b-119">例如， `EndPreventAsyncAbort` 如果未通过第一次调用调用，则在 `BeginPreventAsyncAbort` VM 之前将计数器设置为零。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="a4c4b-120">同样，不检查内部计数器是否溢出。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="a4c4b-121">如果它超过其整数限制，原因是主机和 VM 均递增，则未指定产生的行为。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c4b-122">要求</span><span class="sxs-lookup"><span data-stu-id="a4c4b-122">Requirements</span></span>  
 <span data-ttu-id="a4c4b-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c4b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c4b-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a4c4b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4c4b-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a4c4b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4c4b-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4c4b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c4b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4c4b-127">See also</span></span>

- [<span data-ttu-id="a4c4b-128">BeginPreventAsyncAbort 方法</span><span class="sxs-lookup"><span data-stu-id="a4c4b-128">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="a4c4b-129">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="a4c4b-129">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="a4c4b-130">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a4c4b-130">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a4c4b-131">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a4c4b-131">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a4c4b-132">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a4c4b-132">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="a4c4b-133">承载接口</span><span class="sxs-lookup"><span data-stu-id="a4c4b-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
