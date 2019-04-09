---
title: IHostMemoryManager 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137346"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="8a18b-102">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="8a18b-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="8a18b-103">而不是使用标准 Win32 虚拟内存函数提供允许公共语言运行时 (CLR)，以便通过主机的虚拟内存请求的方法。</span><span class="sxs-lookup"><span data-stu-id="8a18b-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a18b-104">方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-104">Methods</span></span>  
  
|<span data-ttu-id="8a18b-105">方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-105">Method</span></span>|<span data-ttu-id="8a18b-106">描述</span><span class="sxs-lookup"><span data-stu-id="8a18b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a18b-107">AcquiredVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="8a18b-108">通知宿主公共语言运行时 (CLR) 已获得从操作系统指定的内存。</span><span class="sxs-lookup"><span data-stu-id="8a18b-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="8a18b-109">CreateMAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="8a18b-110">获取到的接口指针[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)用于从堆创建主机的请求的内存分配的实例。</span><span class="sxs-lookup"><span data-stu-id="8a18b-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="8a18b-111">GetMemoryLoad 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="8a18b-112">由主机的报告获取当前正在使用的物理内存量。</span><span class="sxs-lookup"><span data-stu-id="8a18b-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="8a18b-113">NeedsVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="8a18b-114">通知宿主，CLR 会尝试使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="8a18b-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="8a18b-115">RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="8a18b-116">注册到通知的计算机上的当前内存负载的 CLR 宿主通过调用的回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="8a18b-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="8a18b-117">ReleasedVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="8a18b-118">通知宿主 CLR 已完成使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="8a18b-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="8a18b-119">VirtualAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="8a18b-120">充当相应的 Win32 函数，将保留或提交的调用进程的虚拟地址空间中的页面区域的逻辑包装器。</span><span class="sxs-lookup"><span data-stu-id="8a18b-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="8a18b-121">VirtualFree 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="8a18b-122">充当相应的 Win32 函数，从而释放，解除，或释放并解除调用进程虚拟地址空间中的页面区域的逻辑包装器。</span><span class="sxs-lookup"><span data-stu-id="8a18b-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="8a18b-123">VirtualProtect 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="8a18b-124">充当相应的 Win32 函数，这会更改调用进程的虚拟地址空间中的提交页面的保护区域上的逻辑包装器。</span><span class="sxs-lookup"><span data-stu-id="8a18b-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="8a18b-125">VirtualQuery 方法</span><span class="sxs-lookup"><span data-stu-id="8a18b-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="8a18b-126">充当相应的 Win32 函数检索有关调用进程的虚拟地址空间中的页范围的信息的逻辑包装器。</span><span class="sxs-lookup"><span data-stu-id="8a18b-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a18b-127">备注</span><span class="sxs-lookup"><span data-stu-id="8a18b-127">Remarks</span></span>  
 `IHostMemoryManager` <span data-ttu-id="8a18b-128">此外提供了方法，以便 CLR 获取要在堆上发出内存请求和获取在过程中，内存压力的级别中的指针，如报告的主机。</span><span class="sxs-lookup"><span data-stu-id="8a18b-128">also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a18b-129">要求</span><span class="sxs-lookup"><span data-stu-id="8a18b-129">Requirements</span></span>  
 <span data-ttu-id="8a18b-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a18b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a18b-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a18b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a18b-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8a18b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8a18b-133">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8a18b-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a18b-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a18b-134">See also</span></span>

- [<span data-ttu-id="8a18b-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="8a18b-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="8a18b-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="8a18b-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
