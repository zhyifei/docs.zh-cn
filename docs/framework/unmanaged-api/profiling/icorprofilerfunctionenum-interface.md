---
title: ICorProfilerFunctionEnum 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e77ec9de198b673bb3b5fc4dad3cd1b0316f07c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092066"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="5e4c7-102">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5e4c7-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="5e4c7-103">提供按顺序循环访问公共语言运行时中的函数集合的方法。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e4c7-104">方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-104">Methods</span></span>  
  
|<span data-ttu-id="5e4c7-105">方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-105">Method</span></span>|<span data-ttu-id="5e4c7-106">描述</span><span class="sxs-lookup"><span data-stu-id="5e4c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e4c7-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="5e4c7-108">获取指向此 `ICorProfilerFunctionEnum` 接口副本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="5e4c7-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="5e4c7-110">获取应用程序加载的函数数量或探查器强制加载的函数数量。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="5e4c7-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="5e4c7-112">从一个函数的顺序集合中获取指定数量的连续函数（从枚举器在序列中的当前位置开始）。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="5e4c7-113">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="5e4c7-114">将枚举器的光标移动到序列的起始位置。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="5e4c7-115">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="5e4c7-116">将枚举器的游标从其当前位置前移，以便跳过指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e4c7-117">备注</span><span class="sxs-lookup"><span data-stu-id="5e4c7-117">Remarks</span></span>  
 <span data-ttu-id="5e4c7-118">`ICorProfilerFunctionEnum` 接口是一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="5e4c7-119">它可以让数组接收器以其合适的速率从发送器拉取元素。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="5e4c7-120">换而言之，接收器可以显式控制数组元素流，从而避免将大型数组作为方法形参传递方面的相关问题。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="5e4c7-121">`ICorProfilerFunctionEnum` 枚举已经过 JIT 编译的函数，但不包括从使用 Ngen.exe 生成的本机映像加载的函数。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e4c7-122">要求</span><span class="sxs-lookup"><span data-stu-id="5e4c7-122">Requirements</span></span>  
 <span data-ttu-id="5e4c7-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4c7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e4c7-124">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e4c7-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e4c7-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e4c7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e4c7-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e4c7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e4c7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e4c7-127">See also</span></span>

- [<span data-ttu-id="5e4c7-128">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5e4c7-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="5e4c7-129">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="5e4c7-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5e4c7-130">EnumJITedFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="5e4c7-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
