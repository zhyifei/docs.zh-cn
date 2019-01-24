---
title: ICorProfilerModuleEnum 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8966a2fc9e38594e8b2727077b7e1e85c3e52b16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705477"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="4ba61-102">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4ba61-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="4ba61-103">提供用于按顺序循环访问应用程序或探查器加载的模块集合的方法。</span><span class="sxs-lookup"><span data-stu-id="4ba61-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ba61-104">方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-104">Methods</span></span>  
  
|<span data-ttu-id="4ba61-105">方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-105">Method</span></span>|<span data-ttu-id="4ba61-106">描述</span><span class="sxs-lookup"><span data-stu-id="4ba61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ba61-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="4ba61-108">获取指向此 `ICorProfilerModuleEnum` 接口副本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="4ba61-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="4ba61-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="4ba61-110">获取已加载到应用程序的托管模块数。</span><span class="sxs-lookup"><span data-stu-id="4ba61-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="4ba61-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="4ba61-112">从对象的序列集合中获取指定的连续模块数，从该序列中的枚举器当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="4ba61-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="4ba61-113">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="4ba61-114">将枚举器的光标移动到序列的起始位置。</span><span class="sxs-lookup"><span data-stu-id="4ba61-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="4ba61-115">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="4ba61-116">前移枚举器的光标位置，以便跳过指定的元素数。</span><span class="sxs-lookup"><span data-stu-id="4ba61-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ba61-117">备注</span><span class="sxs-lookup"><span data-stu-id="4ba61-117">Remarks</span></span>  
 <span data-ttu-id="4ba61-118">`ICorProfilerModuleEnum` 接口是一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="4ba61-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="4ba61-119">它可以让数组接收器以其合适的速率从发送器提取元素。</span><span class="sxs-lookup"><span data-stu-id="4ba61-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="4ba61-120">换而言之，接收器可以显式控制数组元素流，从而避免将大型数组作为方法形参传递方面的相关问题。</span><span class="sxs-lookup"><span data-stu-id="4ba61-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ba61-121">要求</span><span class="sxs-lookup"><span data-stu-id="4ba61-121">Requirements</span></span>  
 <span data-ttu-id="4ba61-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ba61-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba61-123">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ba61-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ba61-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ba61-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ba61-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba61-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba61-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ba61-126">See also</span></span>
- [<span data-ttu-id="4ba61-127">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4ba61-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4ba61-128">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="4ba61-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4ba61-129">EnumModules 方法</span><span class="sxs-lookup"><span data-stu-id="4ba61-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
