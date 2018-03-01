---
title: "IHostMemoryManager 接口"
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
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b39a43874bc1808928f21e0a35638aae9a99ca8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="f29a2-102">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="f29a2-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="f29a2-103">提供允许公共语言运行时 (CLR) 可通过主机，虚拟内存请求的方法，而不是使用标准 Win32 虚拟内存函数。</span><span class="sxs-lookup"><span data-stu-id="f29a2-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f29a2-104">方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-104">Methods</span></span>  
  
|<span data-ttu-id="f29a2-105">方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-105">Method</span></span>|<span data-ttu-id="f29a2-106">描述</span><span class="sxs-lookup"><span data-stu-id="f29a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f29a2-107">AcquiredVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="f29a2-108">通知主机公共语言运行时 (CLR) 已获取从操作系统指定的内存。</span><span class="sxs-lookup"><span data-stu-id="f29a2-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="f29a2-109">CreateMAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="f29a2-110">获取到的接口指针[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)用于从非回收堆由宿主创建请求的内存分配的实例。</span><span class="sxs-lookup"><span data-stu-id="f29a2-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="f29a2-111">GetMemoryLoad 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="f29a2-112">报告的主机，请获取当前正在使用的物理内存量。</span><span class="sxs-lookup"><span data-stu-id="f29a2-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="f29a2-113">NeedsVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="f29a2-114">通知宿主，CLR 将尝试使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="f29a2-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="f29a2-115">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="f29a2-116">注册到主机时，将调用以通知在计算机上的当前内存加载的 CLR 的回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="f29a2-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="f29a2-117">ReleasedVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="f29a2-118">通知主机 CLR 已结束使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="f29a2-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="f29a2-119">VirtualAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="f29a2-120">用作的逻辑包装，相应的 Win32 函数，将保留或提交调用进程虚拟地址空间中的页面的区域。</span><span class="sxs-lookup"><span data-stu-id="f29a2-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="f29a2-121">VirtualFree 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="f29a2-122">用作相应的 Win32 函数，该释放、 解除或释放和解除的调用进程的虚拟地址空间中的页区域函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="f29a2-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="f29a2-123">VirtualProtect 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="f29a2-124">用作更改调用进程的虚拟地址空间中的提交页面的保护区域上的对应 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="f29a2-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="f29a2-125">VirtualQuery 方法</span><span class="sxs-lookup"><span data-stu-id="f29a2-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="f29a2-126">用作检索有关调用进程虚拟地址空间中的页面范围的信息的相应 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="f29a2-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f29a2-127">备注</span><span class="sxs-lookup"><span data-stu-id="f29a2-127">Remarks</span></span>  
 <span data-ttu-id="f29a2-128">`IHostMemoryManager`此外提供了方法，以便 CLR 获取通过其在堆上进行内存请求并获取在过程中，内存压力级别的指针，如报告的主机。</span><span class="sxs-lookup"><span data-stu-id="f29a2-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29a2-129">惠?</span><span class="sxs-lookup"><span data-stu-id="f29a2-129">Requirements</span></span>  
 <span data-ttu-id="f29a2-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f29a2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29a2-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f29a2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f29a2-132">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f29a2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f29a2-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29a2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29a2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f29a2-134">See Also</span></span>  
 [<span data-ttu-id="f29a2-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="f29a2-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="f29a2-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="f29a2-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
