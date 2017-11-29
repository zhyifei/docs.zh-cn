---
title: "ICorProfilerInfo4::GetILToNativeMapping2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetILToNativeMapping2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eda88ca0ba30c85889198e11e3f465b85d1019b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="0ad6f-102">ICorProfilerInfo4::GetILToNativeMapping2 方法</span><span class="sxs-lookup"><span data-stu-id="0ad6f-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="0ad6f-103">针对指定函数的 JIT 重新编译版本中包含的代码，获取 Microsoft 中间语言 (MSIL) 偏移量到本机偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad6f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ad6f-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ad6f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ad6f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0ad6f-106">[in] 包含代码的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="0ad6f-107">[in] JIT 重新编译的函数的标识。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="0ad6f-108">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 中的标识必须为零。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-108">The identity must be zero in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 `cMap`  
 <span data-ttu-id="0ad6f-109">[in] `map` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="0ad6f-110">[out]可用 COR_DEBUG_IL_TO_NATIVE_MAP 结构总数。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="0ad6f-111">[out] `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组，其中每个结构均指定偏移量。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="0ad6f-112">`GetILToNativeMapping2` 方法返回后，`map` 将包含部分或全部 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad6f-113">备注</span><span class="sxs-lookup"><span data-stu-id="0ad6f-113">Remarks</span></span>  
 <span data-ttu-id="0ad6f-114">`GetILToNativeMapping2`类似于[icorprofilerinfo:: Getiltonativemapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)方法，只不过它将允许探查器在将来指定重新编译函数的 ID 版本。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ad6f-115">[Icorprofilerfunctioncontrol::](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)中未实现方法[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，因此已 JIT 重新编译的函数不能拥有的 IL 到本机映射必须不同于最初编译的函数。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="0ad6f-116">同样，不能在 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 中使用 JIT 重新编译的非零 ID 调用 `GetILToNativeMapping2`。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 <span data-ttu-id="0ad6f-117">`GetILToNativeMapping2` 方法返回 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="0ad6f-118">为了表示一定范围的本机指令对应于特殊的代码 （例如，序言） 区域，数组中的条目可以有其`ilOffset`字段设置为值为[CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="0ad6f-119">返回 `GetILToNativeMapping2` 后，必须验证 `map` 缓冲区大小是否足以包含所有 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="0ad6f-120">为此，请将 `cMap` 的值和 `pcMap` 参数的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="0ad6f-121">如果 `pcMap` 值乘以 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的大小所得的值大于 `cMap`，请分配更大的 `map` 缓冲区、将 `cMap` 更新为新的更大大小，并再次调用 `GetILToNativeMapping2`。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="0ad6f-122">或者，可先用长度为零的 `map` 缓冲区调用 `GetILToNativeMapping2` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="0ad6f-123">然后，可将缓冲区大小设置为 `pcMap` 中返回的值，并再次调用 `GetILToNativeMapping2`。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad6f-124">要求</span><span class="sxs-lookup"><span data-stu-id="0ad6f-124">Requirements</span></span>  
 <span data-ttu-id="0ad6f-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ad6f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad6f-126">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ad6f-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ad6f-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad6f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad6f-128">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad6f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad6f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ad6f-129">See Also</span></span>  
 [<span data-ttu-id="0ad6f-130">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="0ad6f-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [<span data-ttu-id="0ad6f-131">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="0ad6f-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="0ad6f-132">分析接口</span><span class="sxs-lookup"><span data-stu-id="0ad6f-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="0ad6f-133">分析</span><span class="sxs-lookup"><span data-stu-id="0ad6f-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
