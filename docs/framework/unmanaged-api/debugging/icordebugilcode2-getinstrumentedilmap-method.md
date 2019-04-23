---
title: ICorDebugILCode2::GetInstrumentedILMap 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4197b018ea85402762a8591b40f3503c02af3974
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222869"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="17542-102">ICorDebugILCode2::GetInstrumentedILMap 方法</span><span class="sxs-lookup"><span data-stu-id="17542-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="17542-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="17542-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="17542-104">返回从探查器检测到的中间语言 (IL) 偏移量到此实例的原始方法的 IL 偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="17542-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17542-105">语法</span><span class="sxs-lookup"><span data-stu-id="17542-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17542-106">参数</span><span class="sxs-lookup"><span data-stu-id="17542-106">Parameters</span></span>  
 <span data-ttu-id="17542-107">cMap</span><span class="sxs-lookup"><span data-stu-id="17542-107">cMap</span></span>  
 <span data-ttu-id="17542-108">[in] `map` 数组的存储容量。</span><span class="sxs-lookup"><span data-stu-id="17542-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="17542-109">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="17542-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="17542-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="17542-110">pcMap</span></span>  
 <span data-ttu-id="17542-111">[out]COR_IL_MAP 值写入映射数组的数目。</span><span class="sxs-lookup"><span data-stu-id="17542-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="17542-112">map</span><span class="sxs-lookup"><span data-stu-id="17542-112">map</span></span>  
 <span data-ttu-id="17542-113">[out]提供的信息在映射从探查器检测到的 IL 到原始方法的 IL 的 COR_IL_MAP 值的数组。</span><span class="sxs-lookup"><span data-stu-id="17542-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17542-114">备注</span><span class="sxs-lookup"><span data-stu-id="17542-114">Remarks</span></span>  
 <span data-ttu-id="17542-115">如果探查器通过调用来设置映射[icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)方法，则调试器可以调用此方法来检索该映射，并计算 IL 偏移量的堆栈时在内部使用该映射跟踪和变量生存期。</span><span class="sxs-lookup"><span data-stu-id="17542-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="17542-116">如果`cMap`为 0 和`pcMap`为非**null**，`pcMap`设置为可用 COR_IL_MAP 值的数目。</span><span class="sxs-lookup"><span data-stu-id="17542-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="17542-117">如果 `map``cMap` 为非零，则它表示  数组的存储容量。</span><span class="sxs-lookup"><span data-stu-id="17542-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="17542-118">方法返回时，`map`最多包含`cMap`项，并`pcMap`设置为实际写入 COR_IL_MAP 值的数目`map`数组。</span><span class="sxs-lookup"><span data-stu-id="17542-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="17542-119">如果尚未检测到 IL 或探查器没有提供映射，则此方法将返回 `S_OK` 并将 `pcMap` 设置为 0。</span><span class="sxs-lookup"><span data-stu-id="17542-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17542-120">要求</span><span class="sxs-lookup"><span data-stu-id="17542-120">Requirements</span></span>  
 <span data-ttu-id="17542-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17542-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17542-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17542-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17542-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17542-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17542-124">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17542-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17542-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="17542-125">See also</span></span>

- [<span data-ttu-id="17542-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="17542-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="17542-127">ICorDebugILCode2 接口</span><span class="sxs-lookup"><span data-stu-id="17542-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="17542-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="17542-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
