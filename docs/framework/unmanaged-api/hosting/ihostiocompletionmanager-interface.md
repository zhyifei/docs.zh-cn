---
title: IHostIoCompletionManager 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186f5618cce7a70bc4fab55616a0f8b08025a81f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542530"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="f2bdf-102">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="f2bdf-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="f2bdf-103">提供允许公共语言运行时 (CLR) 与主机提供的 I/O 完成端口进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2bdf-104">方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-104">Methods</span></span>  
  
|<span data-ttu-id="f2bdf-105">方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-105">Method</span></span>|<span data-ttu-id="f2bdf-106">描述</span><span class="sxs-lookup"><span data-stu-id="f2bdf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2bdf-107">Bind 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="f2bdf-108">将句柄绑定到 I/O 完成端口。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="f2bdf-109">CloseIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="f2bdf-110">关闭通过对的早期调用创建的端口`CreateIoCompletionPort`。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="f2bdf-111">CreateIoCompletionPort 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="f2bdf-112">主机创建新的 I/O 完成端口的请求。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="f2bdf-113">GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="f2bdf-114">获取当前不在处理请求的 I/O 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="f2bdf-115">GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="f2bdf-116">获取宿主要追加到输入/输出请求的任何自定义数据的大小。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="f2bdf-117">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="f2bdf-118">获取为 I/O 请求提供服务的最大主机可以分配的线程数。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="f2bdf-119">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="f2bdf-120">获取为 I/O 请求提供服务的最小主机提供的线程数。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="f2bdf-121">InitializeHostOverlapped 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="f2bdf-122">为宿主提供初始化的 I/O 请求有关的任何自定义数据的机会。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="f2bdf-123">SetCLRIoCompletionManager 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="f2bdf-124">为宿主提供的接口指针到[ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)由 CLR 实现的实例。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="f2bdf-125">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="f2bdf-126">设置为 I/O 请求提供服务的最大主机分配的线程数。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="f2bdf-127">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f2bdf-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="f2bdf-128">将最小主机应分配的线程数设置为 I/O 完成。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2bdf-129">备注</span><span class="sxs-lookup"><span data-stu-id="f2bdf-129">Remarks</span></span>  
 <span data-ttu-id="f2bdf-130">`IHostIoCompletionManager` 对应于`ICLRIoCompletionManager`由 CLR 实现的接口。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="f2bdf-131">CLR 调用的方法`IHostIoCompletionManager`若要将句柄绑定到宿主提供，并且宿主调用的方法的端口`ICLRIoCompletionManager`报告的 I/O 请求完成。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2bdf-132">要求</span><span class="sxs-lookup"><span data-stu-id="f2bdf-132">Requirements</span></span>  
 <span data-ttu-id="f2bdf-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2bdf-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2bdf-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2bdf-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2bdf-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2bdf-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2bdf-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2bdf-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bdf-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2bdf-137">See also</span></span>
- [<span data-ttu-id="f2bdf-138">承载接口</span><span class="sxs-lookup"><span data-stu-id="f2bdf-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
