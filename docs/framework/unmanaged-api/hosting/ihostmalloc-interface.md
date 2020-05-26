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
ms.openlocfilehash: 8f4e1cd7586df7d8e2a577d26f06eaed6b2c8bb7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804607"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="f52a3-102">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="f52a3-102">IHostMalloc Interface</span></span>
<span data-ttu-id="f52a3-103">提供允许公共语言运行时（CLR）通过宿主请求从堆进行细化分配的方法。</span><span class="sxs-lookup"><span data-stu-id="f52a3-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f52a3-104">方法</span><span class="sxs-lookup"><span data-stu-id="f52a3-104">Methods</span></span>  
  
|<span data-ttu-id="f52a3-105">方法</span><span class="sxs-lookup"><span data-stu-id="f52a3-105">Method</span></span>|<span data-ttu-id="f52a3-106">说明</span><span class="sxs-lookup"><span data-stu-id="f52a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f52a3-107">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="f52a3-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="f52a3-108">请求宿主从堆分配请求的内存量。</span><span class="sxs-lookup"><span data-stu-id="f52a3-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="f52a3-109">DebugAlloc 方法</span><span class="sxs-lookup"><span data-stu-id="f52a3-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="f52a3-110">请求宿主从堆分配请求的内存量，并另外跟踪内存的分配位置。</span><span class="sxs-lookup"><span data-stu-id="f52a3-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="f52a3-111">Free 方法</span><span class="sxs-lookup"><span data-stu-id="f52a3-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="f52a3-112">释放通过使用方法分配的内存 `Alloc` 。</span><span class="sxs-lookup"><span data-stu-id="f52a3-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f52a3-113">备注</span><span class="sxs-lookup"><span data-stu-id="f52a3-113">Remarks</span></span>  
 <span data-ttu-id="f52a3-114">CLR `IHostMalloc` 通过调用[IHostMemoryManager：： CreateMalloc](ihostmemorymanager-createmalloc-method.md)方法获取指向实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f52a3-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f52a3-115">要求</span><span class="sxs-lookup"><span data-stu-id="f52a3-115">Requirements</span></span>  
 <span data-ttu-id="f52a3-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f52a3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f52a3-117">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f52a3-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f52a3-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f52a3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f52a3-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f52a3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52a3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f52a3-120">See also</span></span>

- [<span data-ttu-id="f52a3-121">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="f52a3-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="f52a3-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="f52a3-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
