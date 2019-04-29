---
title: IHostThreadPoolManager 接口
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e7976740a79efda8e5ab569f2efb55444012c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796546"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="c4666-102">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4666-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="c4666-103">提供启用公共语言运行时 (CLR)，配置该线程池，排队到线程池的工作项的方法。</span><span class="sxs-lookup"><span data-stu-id="c4666-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4666-104">方法</span><span class="sxs-lookup"><span data-stu-id="c4666-104">Methods</span></span>  
  
|<span data-ttu-id="c4666-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4666-105">Method</span></span>|<span data-ttu-id="c4666-106">描述</span><span class="sxs-lookup"><span data-stu-id="c4666-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4666-107">GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c4666-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="c4666-108">获取当前不在处理工作项在线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="c4666-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="c4666-109">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c4666-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="c4666-110">在线程池中同时获取的最大主机维护的线程数。</span><span class="sxs-lookup"><span data-stu-id="c4666-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="c4666-111">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c4666-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="c4666-112">预期的请求获取最小主机维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="c4666-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="c4666-113">QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="c4666-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="c4666-114">排队的执行，一个函数，并提供了一个包含该函数使用的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="c4666-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="c4666-115">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c4666-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="c4666-116">设置最大主机可以维护在线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="c4666-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="c4666-117">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="c4666-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="c4666-118">设置预期的请求的最小的主机必须维护的空闲线程数。</span><span class="sxs-lookup"><span data-stu-id="c4666-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4666-119">备注</span><span class="sxs-lookup"><span data-stu-id="c4666-119">Remarks</span></span>  
 <span data-ttu-id="c4666-120">主机不需要使用对的调用中指定的值配置的线程池`SetMaxThreads`和`SetMinThreads`方法。</span><span class="sxs-lookup"><span data-stu-id="c4666-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="c4666-121">在这种情况下，主机应从这些方法返回 E_NOTIMPL HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="c4666-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4666-122">要求</span><span class="sxs-lookup"><span data-stu-id="c4666-122">Requirements</span></span>  
 <span data-ttu-id="c4666-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4666-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4666-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4666-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4666-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c4666-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4666-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4666-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4666-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4666-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c4666-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="c4666-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
