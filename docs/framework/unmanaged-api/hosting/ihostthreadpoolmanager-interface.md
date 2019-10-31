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
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122074"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="a5594-102">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="a5594-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="a5594-103">提供一些方法，使公共语言运行时（CLR）可以配置线程池并将工作项排队到线程池。</span><span class="sxs-lookup"><span data-stu-id="a5594-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5594-104">方法</span><span class="sxs-lookup"><span data-stu-id="a5594-104">Methods</span></span>  
  
|<span data-ttu-id="a5594-105">方法</span><span class="sxs-lookup"><span data-stu-id="a5594-105">Method</span></span>|<span data-ttu-id="a5594-106">描述</span><span class="sxs-lookup"><span data-stu-id="a5594-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5594-107">GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="a5594-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="a5594-108">获取线程池中当前未处理工作项的线程的数目。</span><span class="sxs-lookup"><span data-stu-id="a5594-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="a5594-109">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="a5594-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="a5594-110">获取主机在线程池中并发维护的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="a5594-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="a5594-111">GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="a5594-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="a5594-112">获取主机为获得请求而保留的空闲线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="a5594-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="a5594-113">QueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="a5594-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="a5594-114">将函数排队以便执行，并提供包含函数要使用的数据的对象。</span><span class="sxs-lookup"><span data-stu-id="a5594-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="a5594-115">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="a5594-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="a5594-116">设置宿主可在线程池中维护的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="a5594-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="a5594-117">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="a5594-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="a5594-118">设置主机在预期请求中必须保持的空闲线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="a5594-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5594-119">备注</span><span class="sxs-lookup"><span data-stu-id="a5594-119">Remarks</span></span>  
 <span data-ttu-id="a5594-120">主机不需要使用对 `SetMaxThreads` 和 `SetMinThreads` 方法的调用中指定的值来配置线程池。</span><span class="sxs-lookup"><span data-stu-id="a5594-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="a5594-121">在这种情况下，宿主应从这些方法返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="a5594-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5594-122">要求</span><span class="sxs-lookup"><span data-stu-id="a5594-122">Requirements</span></span>  
 <span data-ttu-id="a5594-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5594-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5594-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a5594-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5594-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a5594-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5594-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5594-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5594-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5594-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a5594-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="a5594-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
