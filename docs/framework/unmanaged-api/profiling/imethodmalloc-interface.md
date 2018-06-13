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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b11cf0fadc9142ee291115cf9f0d84e6429834fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455112"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="12c30-102">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="12c30-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="12c30-103">提供的方法来为新的 Microsoft 中间语言 (MSIL) 函数主体分配内存。</span><span class="sxs-lookup"><span data-stu-id="12c30-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12c30-104">`IMethodMalloc`接口是一个简单的内存的分配器。</span><span class="sxs-lookup"><span data-stu-id="12c30-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="12c30-105">它允许你来分配内存，但不是能将其释放。</span><span class="sxs-lookup"><span data-stu-id="12c30-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12c30-106">方法</span><span class="sxs-lookup"><span data-stu-id="12c30-106">Methods</span></span>  
  
|<span data-ttu-id="12c30-107">方法</span><span class="sxs-lookup"><span data-stu-id="12c30-107">Method</span></span>|<span data-ttu-id="12c30-108">描述</span><span class="sxs-lookup"><span data-stu-id="12c30-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12c30-109">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="12c30-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="12c30-110">尝试为新的 MSIL 函数体分配指定的数量的内存。</span><span class="sxs-lookup"><span data-stu-id="12c30-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12c30-111">备注</span><span class="sxs-lookup"><span data-stu-id="12c30-111">Remarks</span></span>  
 <span data-ttu-id="12c30-112">每个分配器是特定于模块的并确保函数体将模块的基正偏移量的位置。</span><span class="sxs-lookup"><span data-stu-id="12c30-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="12c30-113">上面的模块的基的内存会宝贵，所以用于仅为函数主体分配内存分配器。</span><span class="sxs-lookup"><span data-stu-id="12c30-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12c30-114">要求</span><span class="sxs-lookup"><span data-stu-id="12c30-114">Requirements</span></span>  
 <span data-ttu-id="12c30-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12c30-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12c30-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12c30-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12c30-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12c30-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12c30-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12c30-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c30-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="12c30-119">See Also</span></span>  
 [<span data-ttu-id="12c30-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="12c30-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
