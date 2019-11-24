---
title: IMethodMalloc 接口
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447550"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="4899c-102">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="4899c-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="4899c-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span><span class="sxs-lookup"><span data-stu-id="4899c-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4899c-104">The `IMethodMalloc` interface is a simple memory allocator.</span><span class="sxs-lookup"><span data-stu-id="4899c-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="4899c-105">It allows you to allocate memory, but not to free it.</span><span class="sxs-lookup"><span data-stu-id="4899c-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4899c-106">方法</span><span class="sxs-lookup"><span data-stu-id="4899c-106">Methods</span></span>  
  
|<span data-ttu-id="4899c-107">方法</span><span class="sxs-lookup"><span data-stu-id="4899c-107">Method</span></span>|<span data-ttu-id="4899c-108">描述</span><span class="sxs-lookup"><span data-stu-id="4899c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4899c-109">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="4899c-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="4899c-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span><span class="sxs-lookup"><span data-stu-id="4899c-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4899c-111">备注</span><span class="sxs-lookup"><span data-stu-id="4899c-111">Remarks</span></span>  
 <span data-ttu-id="4899c-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span><span class="sxs-lookup"><span data-stu-id="4899c-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="4899c-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span><span class="sxs-lookup"><span data-stu-id="4899c-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4899c-114">要求</span><span class="sxs-lookup"><span data-stu-id="4899c-114">Requirements</span></span>  
 <span data-ttu-id="4899c-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4899c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4899c-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4899c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4899c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4899c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4899c-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4899c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4899c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4899c-119">See also</span></span>

- [<span data-ttu-id="4899c-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="4899c-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
