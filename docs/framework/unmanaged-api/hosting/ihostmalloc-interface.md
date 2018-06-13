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
ms.openlocfilehash: bbf889aaa6a78e67d0f08758adc0bf31cd932e88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441343"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="6666e-102">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="6666e-102">IHostMalloc Interface</span></span>
<span data-ttu-id="6666e-103">提供允许公共语言运行时 (CLR) 主机通过从堆请求细粒度分配的方法。</span><span class="sxs-lookup"><span data-stu-id="6666e-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6666e-104">方法</span><span class="sxs-lookup"><span data-stu-id="6666e-104">Methods</span></span>  
  
|<span data-ttu-id="6666e-105">方法</span><span class="sxs-lookup"><span data-stu-id="6666e-105">Method</span></span>|<span data-ttu-id="6666e-106">描述</span><span class="sxs-lookup"><span data-stu-id="6666e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6666e-107">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="6666e-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="6666e-108">主机从堆分配请求的内存量的请求。</span><span class="sxs-lookup"><span data-stu-id="6666e-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="6666e-109">DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="6666e-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="6666e-110">请求主机从堆中，分配请求的内存量和此外跟踪分配内存时。</span><span class="sxs-lookup"><span data-stu-id="6666e-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="6666e-111">Free 方法</span><span class="sxs-lookup"><span data-stu-id="6666e-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="6666e-112">释放使用分配的内存`Alloc`方法。</span><span class="sxs-lookup"><span data-stu-id="6666e-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6666e-113">备注</span><span class="sxs-lookup"><span data-stu-id="6666e-113">Remarks</span></span>  
 <span data-ttu-id="6666e-114">CLR 获取到的接口指针`IHostMalloc`实例通过调用[ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6666e-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6666e-115">要求</span><span class="sxs-lookup"><span data-stu-id="6666e-115">Requirements</span></span>  
 <span data-ttu-id="6666e-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6666e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6666e-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6666e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6666e-118">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6666e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6666e-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6666e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6666e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6666e-120">See Also</span></span>  
 [<span data-ttu-id="6666e-121">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="6666e-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="6666e-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="6666e-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
