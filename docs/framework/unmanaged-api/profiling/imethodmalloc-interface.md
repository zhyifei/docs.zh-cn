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
ms.openlocfilehash: 6f5c21d329ed35f82e36c2d88ac911401799e820
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596015"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="d654f-102">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="d654f-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="d654f-103">提供用于新的 Microsoft 中间语言 (MSIL) 函数主体分配内存的方法。</span><span class="sxs-lookup"><span data-stu-id="d654f-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d654f-104">`IMethodMalloc`接口是一个简单的内存分配器。</span><span class="sxs-lookup"><span data-stu-id="d654f-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="d654f-105">它可以分配内存，但不是能将其释放。</span><span class="sxs-lookup"><span data-stu-id="d654f-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d654f-106">方法</span><span class="sxs-lookup"><span data-stu-id="d654f-106">Methods</span></span>  
  
|<span data-ttu-id="d654f-107">方法</span><span class="sxs-lookup"><span data-stu-id="d654f-107">Method</span></span>|<span data-ttu-id="d654f-108">描述</span><span class="sxs-lookup"><span data-stu-id="d654f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d654f-109">Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="d654f-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="d654f-110">尝试为新的 MSIL 函数体分配指定的内存量。</span><span class="sxs-lookup"><span data-stu-id="d654f-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d654f-111">备注</span><span class="sxs-lookup"><span data-stu-id="d654f-111">Remarks</span></span>  
 <span data-ttu-id="d654f-112">每个分配器是特定于模块的并确保函数体，将从该模块的基的正偏移位置。</span><span class="sxs-lookup"><span data-stu-id="d654f-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="d654f-113">因此，应使用分配器分配内存来存放函数体仅，十分宝贵，模块的基以上的内存。</span><span class="sxs-lookup"><span data-stu-id="d654f-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d654f-114">要求</span><span class="sxs-lookup"><span data-stu-id="d654f-114">Requirements</span></span>  
 <span data-ttu-id="d654f-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d654f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d654f-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d654f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d654f-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d654f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d654f-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d654f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d654f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d654f-119">See also</span></span>
- [<span data-ttu-id="d654f-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="d654f-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
