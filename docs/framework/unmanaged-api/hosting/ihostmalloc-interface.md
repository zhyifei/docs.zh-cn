---
title: "IHostMalloc 接口"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="1ae19-102">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="1ae19-102">IHostMalloc Interface</span></span>
<span data-ttu-id="1ae19-103">提供允许公共语言运行时 (CLR) 主机通过从堆请求细粒度分配的方法。</span><span class="sxs-lookup"><span data-stu-id="1ae19-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ae19-104">方法</span><span class="sxs-lookup"><span data-stu-id="1ae19-104">Methods</span></span>  
  
|<span data-ttu-id="1ae19-105">方法</span><span class="sxs-lookup"><span data-stu-id="1ae19-105">Method</span></span>|<span data-ttu-id="1ae19-106">描述</span><span class="sxs-lookup"><span data-stu-id="1ae19-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ae19-107">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="1ae19-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="1ae19-108">主机从堆分配请求的内存量的请求。</span><span class="sxs-lookup"><span data-stu-id="1ae19-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="1ae19-109">DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="1ae19-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="1ae19-110">请求主机从堆中，分配请求的内存量和此外跟踪分配内存时。</span><span class="sxs-lookup"><span data-stu-id="1ae19-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="1ae19-111">Free 方法</span><span class="sxs-lookup"><span data-stu-id="1ae19-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="1ae19-112">释放使用分配的内存`Alloc`方法。</span><span class="sxs-lookup"><span data-stu-id="1ae19-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ae19-113">备注</span><span class="sxs-lookup"><span data-stu-id="1ae19-113">Remarks</span></span>  
 <span data-ttu-id="1ae19-114">CLR 获取到的接口指针`IHostMalloc`实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1ae19-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae19-115">惠?</span><span class="sxs-lookup"><span data-stu-id="1ae19-115">Requirements</span></span>  
 <span data-ttu-id="1ae19-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ae19-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae19-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ae19-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ae19-118">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1ae19-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ae19-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae19-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae19-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ae19-120">See Also</span></span>  
 [<span data-ttu-id="1ae19-121">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="1ae19-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="1ae19-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="1ae19-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
