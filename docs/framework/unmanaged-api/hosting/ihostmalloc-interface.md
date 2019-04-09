---
title: IHostMalloc 接口
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136404"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="70058-102">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="70058-102">IHostMalloc Interface</span></span>
<span data-ttu-id="70058-103">提供使公共语言运行时 (CLR) 从通过主机堆请求细粒度分配方法。</span><span class="sxs-lookup"><span data-stu-id="70058-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70058-104">方法</span><span class="sxs-lookup"><span data-stu-id="70058-104">Methods</span></span>  
  
|<span data-ttu-id="70058-105">方法</span><span class="sxs-lookup"><span data-stu-id="70058-105">Method</span></span>|<span data-ttu-id="70058-106">描述</span><span class="sxs-lookup"><span data-stu-id="70058-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70058-107">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="70058-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="70058-108">请求主机从堆分配请求的内存量。</span><span class="sxs-lookup"><span data-stu-id="70058-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="70058-109">DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="70058-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="70058-110">请求主机从堆分配请求的内存量和此外来跟踪分配内存时。</span><span class="sxs-lookup"><span data-stu-id="70058-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="70058-111">Free 方法</span><span class="sxs-lookup"><span data-stu-id="70058-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="70058-112">释放由使用分配的内存`Alloc`方法。</span><span class="sxs-lookup"><span data-stu-id="70058-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70058-113">备注</span><span class="sxs-lookup"><span data-stu-id="70058-113">Remarks</span></span>  
 <span data-ttu-id="70058-114">CLR 获取到的接口指针`IHostMalloc`实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="70058-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70058-115">要求</span><span class="sxs-lookup"><span data-stu-id="70058-115">Requirements</span></span>  
 <span data-ttu-id="70058-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70058-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70058-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70058-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70058-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="70058-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="70058-119">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="70058-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70058-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="70058-120">See also</span></span>

- [<span data-ttu-id="70058-121">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="70058-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="70058-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="70058-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
