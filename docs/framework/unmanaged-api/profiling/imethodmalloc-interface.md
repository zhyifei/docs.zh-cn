---
title: "IMethodMalloc 接口"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1941a46a60219d9dd56d162f89baf268f220c102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="c5ec1-102">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="c5ec1-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="c5ec1-103">提供的方法来为新的 Microsoft 中间语言 (MSIL) 函数主体分配内存。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5ec1-104">`IMethodMalloc`接口是一个简单的内存的分配器。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="c5ec1-105">它允许你来分配内存，但不是能将其释放。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5ec1-106">方法</span><span class="sxs-lookup"><span data-stu-id="c5ec1-106">Methods</span></span>  
  
|<span data-ttu-id="c5ec1-107">方法</span><span class="sxs-lookup"><span data-stu-id="c5ec1-107">Method</span></span>|<span data-ttu-id="c5ec1-108">描述</span><span class="sxs-lookup"><span data-stu-id="c5ec1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5ec1-109">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="c5ec1-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="c5ec1-110">尝试为新的 MSIL 函数体分配指定的数量的内存。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5ec1-111">备注</span><span class="sxs-lookup"><span data-stu-id="c5ec1-111">Remarks</span></span>  
 <span data-ttu-id="c5ec1-112">每个分配器是特定于模块的并确保函数体将模块的基正偏移量的位置。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="c5ec1-113">上面的模块的基的内存会宝贵，所以用于仅为函数主体分配内存分配器。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5ec1-114">惠?</span><span class="sxs-lookup"><span data-stu-id="c5ec1-114">Requirements</span></span>  
 <span data-ttu-id="c5ec1-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ec1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5ec1-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5ec1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5ec1-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5ec1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5ec1-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5ec1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ec1-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5ec1-119">See Also</span></span>  
 [<span data-ttu-id="c5ec1-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="c5ec1-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
