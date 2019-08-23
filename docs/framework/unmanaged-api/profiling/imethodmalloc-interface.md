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
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935651"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="ed850-102">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="ed850-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="ed850-103">提供一个方法, 用于为新的 Microsoft 中间语言 (MSIL) 函数体分配内存。</span><span class="sxs-lookup"><span data-stu-id="ed850-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed850-104">`IMethodMalloc`接口是一个简单的内存分配器。</span><span class="sxs-lookup"><span data-stu-id="ed850-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="ed850-105">它允许您分配内存, 但不能释放内存。</span><span class="sxs-lookup"><span data-stu-id="ed850-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed850-106">方法</span><span class="sxs-lookup"><span data-stu-id="ed850-106">Methods</span></span>  
  
|<span data-ttu-id="ed850-107">方法</span><span class="sxs-lookup"><span data-stu-id="ed850-107">Method</span></span>|<span data-ttu-id="ed850-108">描述</span><span class="sxs-lookup"><span data-stu-id="ed850-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed850-109">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="ed850-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="ed850-110">尝试为新的 MSIL 函数体分配指定的内存量。</span><span class="sxs-lookup"><span data-stu-id="ed850-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed850-111">备注</span><span class="sxs-lookup"><span data-stu-id="ed850-111">Remarks</span></span>  
 <span data-ttu-id="ed850-112">每个分配器都是特定于模块的, 并确保函数体与模块的基偏移为正偏移量。</span><span class="sxs-lookup"><span data-stu-id="ed850-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="ed850-113">超出模块基的内存可能非常宝贵, 因此应使用分配器仅为函数体分配内存。</span><span class="sxs-lookup"><span data-stu-id="ed850-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed850-114">要求</span><span class="sxs-lookup"><span data-stu-id="ed850-114">Requirements</span></span>  
 <span data-ttu-id="ed850-115">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed850-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed850-116">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="ed850-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed850-117">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed850-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed850-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed850-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed850-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed850-119">See also</span></span>

- [<span data-ttu-id="ed850-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="ed850-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
