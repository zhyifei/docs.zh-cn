---
title: ICorProfilerInfo4 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: cbd7c0d8fff55766a98e727ce22c77dd5214611b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448005"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="b1e87-102">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="b1e87-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="b1e87-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span><span class="sxs-lookup"><span data-stu-id="b1e87-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="b1e87-104">方法。</span><span class="sxs-lookup"><span data-stu-id="b1e87-104">.</span></span> <span data-ttu-id="b1e87-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="b1e87-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="b1e87-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b1e87-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1e87-107">方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-107">Methods</span></span>  
  
|<span data-ttu-id="b1e87-108">方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-108">Method</span></span>|<span data-ttu-id="b1e87-109">描述</span><span class="sxs-lookup"><span data-stu-id="b1e87-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1e87-110">EnumJITedFunctions2 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="b1e87-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span><span class="sxs-lookup"><span data-stu-id="b1e87-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="b1e87-112">EnumThreads 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="b1e87-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span><span class="sxs-lookup"><span data-stu-id="b1e87-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="b1e87-114">GetCodeInfo3 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="b1e87-115">获取本机代码的范围，该代码与指定函数的 JIT 重新编译版本相关联。</span><span class="sxs-lookup"><span data-stu-id="b1e87-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="b1e87-116">GetFunctionFromIP2 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="b1e87-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span><span class="sxs-lookup"><span data-stu-id="b1e87-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="b1e87-118">GetILToNativeMapping2 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="b1e87-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span><span class="sxs-lookup"><span data-stu-id="b1e87-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="b1e87-120">GetObjectSize2 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="b1e87-121">Returns the size of a specified object.</span><span class="sxs-lookup"><span data-stu-id="b1e87-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="b1e87-122">GetReJITIDs 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="b1e87-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span><span class="sxs-lookup"><span data-stu-id="b1e87-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="b1e87-124">InitializeCurrentThread 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="b1e87-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span><span class="sxs-lookup"><span data-stu-id="b1e87-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="b1e87-126">RequestReJIT 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="b1e87-127">请求 JIT 重新编译指定函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="b1e87-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="b1e87-128">RequestRevert 方法</span><span class="sxs-lookup"><span data-stu-id="b1e87-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="b1e87-129">将指定函数的所有实例还原为其初始版本。</span><span class="sxs-lookup"><span data-stu-id="b1e87-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1e87-130">备注</span><span class="sxs-lookup"><span data-stu-id="b1e87-130">Remarks</span></span>  
 <span data-ttu-id="b1e87-131">CLR 通过使用自由线程模型实现 `ICorProfilerInfo4` 接口的方法。</span><span class="sxs-lookup"><span data-stu-id="b1e87-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="b1e87-132">每个方法均返回一个 HRESULT，指示成功或失败。</span><span class="sxs-lookup"><span data-stu-id="b1e87-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="b1e87-133">有关可能的返回代码的列表，请参阅 CorError.h 文件。</span><span class="sxs-lookup"><span data-stu-id="b1e87-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1e87-134">要求</span><span class="sxs-lookup"><span data-stu-id="b1e87-134">Requirements</span></span>  
 <span data-ttu-id="b1e87-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e87-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e87-136">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1e87-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1e87-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1e87-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1e87-138">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e87-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e87-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1e87-139">See also</span></span>

- [<span data-ttu-id="b1e87-140">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="b1e87-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b1e87-141">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b1e87-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
