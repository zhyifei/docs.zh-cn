---
title: IMethodMalloc::Alloc 方法
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d73fe16720248d541bac64a432bb6f35d6873b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454976"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="8e76d-102">IMethodMalloc::Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="8e76d-102">IMethodMalloc::Alloc Method</span></span>
<span data-ttu-id="8e76d-103">尝试为新的 Microsoft 中间语言 (MSIL) 函数主体分配指定的数量的内存。</span><span class="sxs-lookup"><span data-stu-id="8e76d-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e76d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e76d-104">Syntax</span></span>  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e76d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e76d-105">Parameters</span></span>  
 `cb`  
 <span data-ttu-id="8e76d-106">[in]要为方法体分配的字节数。</span><span class="sxs-lookup"><span data-stu-id="8e76d-106">[in] The number of bytes to allocate for the method body.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e76d-107">备注</span><span class="sxs-lookup"><span data-stu-id="8e76d-107">Remarks</span></span>  
 <span data-ttu-id="8e76d-108">分配的内存将大于与此分配器相关联的模块的基址的地址处开始。</span><span class="sxs-lookup"><span data-stu-id="8e76d-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="8e76d-109">换而言之，每个分配器创建对特定模块，并且将尝试从其基址分配正偏移量的内存。</span><span class="sxs-lookup"><span data-stu-id="8e76d-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="8e76d-110">如果`Alloc`无法分配的请求大于该模块的基址的地址处的字节数它将返回 E_OUTOFMEMORY，而不考虑实际可用的内存空间量。</span><span class="sxs-lookup"><span data-stu-id="8e76d-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>  
  
 <span data-ttu-id="8e76d-111">`Alloc`方法应与结合使用[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8e76d-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e76d-112">要求</span><span class="sxs-lookup"><span data-stu-id="8e76d-112">Requirements</span></span>  
 <span data-ttu-id="8e76d-113">**平台：** WindSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e76d-113">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e76d-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e76d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e76d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e76d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e76d-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e76d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e76d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e76d-117">See Also</span></span>  
 [<span data-ttu-id="8e76d-118">IMethodMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="8e76d-118">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
