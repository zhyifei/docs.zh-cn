---
title: "ICorProfilerFunctionEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum
helpviewer_keywords: ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1067fa6738b23492b3a58500b4cb6ba1d030304f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="92ab4-102">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="92ab4-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="92ab4-103">提供按顺序循环访问公共语言运行时中的函数集合的方法。</span><span class="sxs-lookup"><span data-stu-id="92ab4-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92ab4-104">方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-104">Methods</span></span>  
  
|<span data-ttu-id="92ab4-105">方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-105">Method</span></span>|<span data-ttu-id="92ab4-106">描述</span><span class="sxs-lookup"><span data-stu-id="92ab4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92ab4-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="92ab4-108">获取指向此 `ICorProfilerFunctionEnum` 接口副本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="92ab4-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="92ab4-109">GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="92ab4-110">获取应用程序加载的函数数量或探查器强制加载的函数数量。</span><span class="sxs-lookup"><span data-stu-id="92ab4-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="92ab4-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="92ab4-112">从一个函数的顺序集合中获取指定数量的连续函数（从枚举器在序列中的当前位置开始）。</span><span class="sxs-lookup"><span data-stu-id="92ab4-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="92ab4-113">Reset 方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="92ab4-114">将枚举器的光标移动到序列的起始位置。</span><span class="sxs-lookup"><span data-stu-id="92ab4-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="92ab4-115">Skip 方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="92ab4-116">将枚举器的游标从其当前位置前移，以便跳过指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="92ab4-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92ab4-117">备注</span><span class="sxs-lookup"><span data-stu-id="92ab4-117">Remarks</span></span>  
 <span data-ttu-id="92ab4-118">`ICorProfilerFunctionEnum` 接口是一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="92ab4-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="92ab4-119">它可以让数组接收器以其合适的速率从发送器提取元素。</span><span class="sxs-lookup"><span data-stu-id="92ab4-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="92ab4-120">换而言之，接收器可以显式控制数组元素流，从而避免将大型数组作为方法形参传递方面的相关问题。</span><span class="sxs-lookup"><span data-stu-id="92ab4-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="92ab4-121">`ICorProfilerFunctionEnum` 枚举已经过 JIT 编译的函数，但不包括从使用 Ngen.exe 生成的本机映像加载的函数。</span><span class="sxs-lookup"><span data-stu-id="92ab4-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ab4-122">要求</span><span class="sxs-lookup"><span data-stu-id="92ab4-122">Requirements</span></span>  
 <span data-ttu-id="92ab4-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92ab4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ab4-124">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92ab4-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92ab4-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ab4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ab4-126">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ab4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ab4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92ab4-127">See Also</span></span>  
 [<span data-ttu-id="92ab4-128">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="92ab4-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="92ab4-129">分析接口</span><span class="sxs-lookup"><span data-stu-id="92ab4-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="92ab4-130">EnumJITedFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="92ab4-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
