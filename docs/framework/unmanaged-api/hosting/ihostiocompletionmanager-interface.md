---
title: "IHostIoCompletionManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cbb4b87b57d4f5e11a9dab04d20dfb73170bb4a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="c7bd6-102">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="c7bd6-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="c7bd6-103">提供允许公共语言运行时 (CLR) 与主机提供的 I/O 完成端口进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7bd6-104">方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-104">Methods</span></span>  
  
|<span data-ttu-id="c7bd6-105">方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-105">Method</span></span>|<span data-ttu-id="c7bd6-106">描述</span><span class="sxs-lookup"><span data-stu-id="c7bd6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7bd6-107">Bind 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="c7bd6-108">将句柄绑定到 I/O 完成端口。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="c7bd6-109">CloseIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="c7bd6-110">关闭通过以前调用创建的端口`CreateIoCompletionPort`。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="c7bd6-111">CreateIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="c7bd6-112">主机创建新的 I/O 完成端口的请求。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="c7bd6-113">GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="c7bd6-114">获取当前不在处理请求的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="c7bd6-115">GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="c7bd6-116">获取宿主要追加到输入/输出请求的任何自定义数据的大小。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="c7bd6-117">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="c7bd6-118">获取服务输入/输出请求的最大主机可以分配的线程数。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="c7bd6-119">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="c7bd6-120">获取服务输入/输出请求的最小主机提供的线程数。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="c7bd6-121">InitializeHostOverlapped 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="c7bd6-122">若要初始化的 I/O 请求有关的任何自定义数据的机会提供主机。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="c7bd6-123">SetCLRIoCompletionManager 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="c7bd6-124">为宿主提供的接口指针到[ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)由 CLR 实现的实例。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="c7bd6-125">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="c7bd6-126">将最大主机分配的线程数设置为服务输入/输出请求。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="c7bd6-127">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c7bd6-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="c7bd6-128">将最小应分配主机的线程数设置为 I/O 完成。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7bd6-129">备注</span><span class="sxs-lookup"><span data-stu-id="c7bd6-129">Remarks</span></span>  
 <span data-ttu-id="c7bd6-130">`IHostIoCompletionManager`对应于`ICLRIoCompletionManager`由 CLR 实现接口。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="c7bd6-131">CLR 调用的方法`IHostIoCompletionManager`将句柄绑定到主机提供，并且宿主调用的方法的端口`ICLRIoCompletionManager`报告 I/O 请求的完成。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7bd6-132">惠?</span><span class="sxs-lookup"><span data-stu-id="c7bd6-132">Requirements</span></span>  
 <span data-ttu-id="c7bd6-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7bd6-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7bd6-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7bd6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7bd6-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c7bd6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7bd6-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7bd6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bd6-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7bd6-137">See Also</span></span>  
 [<span data-ttu-id="c7bd6-138">承载接口</span><span class="sxs-lookup"><span data-stu-id="c7bd6-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
