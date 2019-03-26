---
title: ICorProfilerInfo::GetILToNativeMapping 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea179c679018f7bfd9c8948823628ddb5a38491
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489756"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="a5ff9-102">ICorProfilerInfo::GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="a5ff9-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>
<span data-ttu-id="a5ff9-103">针对指定函数中包含的代码，获取 Microsoft 中间语言 (MSIL) 偏移量到本机偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ff9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5ff9-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5ff9-105">参数</span><span class="sxs-lookup"><span data-stu-id="a5ff9-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a5ff9-106">[in] 包含代码的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="a5ff9-107">[in] `map` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="a5ff9-108">[out]可用 COR_DEBUG_IL_TO_NATIVE_MAP 结构总数。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="a5ff9-109">[out] `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组，其中每个结构均指定偏移量。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="a5ff9-110">`GetILToNativeMapping` 方法返回后，`map` 将包含部分或全部 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5ff9-111">备注</span><span class="sxs-lookup"><span data-stu-id="a5ff9-111">Remarks</span></span>  
 <span data-ttu-id="a5ff9-112">`GetILToNativeMapping` 方法返回 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="a5ff9-113">若要表达特定范围的本机指令对应的代码 (例如，prolog) 的特殊区域，该数组中的条目可以有其`ilOffset`字段设置为值[CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="a5ff9-114">返回 `GetILToNativeMapping` 后，必须验证 `map` 缓冲区大小是否足以包含所有 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="a5ff9-115">为此，请将 `cMap` 的值和 `pcMap` 参数的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="a5ff9-116">如果 `pcMap` 值乘以 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的大小所得的值大于 `cMap`，请分配更大的 `map` 缓冲区、将 `cMap` 更新为新的更大大小，并再次调用 `GetILToNativeMapping`。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="a5ff9-117">或者，可以先用长度为零的 `map` 缓冲区调用 `GetILToNativeMapping` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="a5ff9-118">然后，可将缓冲区大小设置为 `pcMap` 中返回的值，并再次调用 `GetILToNativeMapping`。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ff9-119">要求</span><span class="sxs-lookup"><span data-stu-id="a5ff9-119">Requirements</span></span>  
 <span data-ttu-id="a5ff9-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ff9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ff9-121">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5ff9-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5ff9-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5ff9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5ff9-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5ff9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ff9-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5ff9-124">See also</span></span>
- [<span data-ttu-id="a5ff9-125">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="a5ff9-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="a5ff9-126">GetILToNativeMapping2 方法</span><span class="sxs-lookup"><span data-stu-id="a5ff9-126">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="a5ff9-127">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="a5ff9-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a5ff9-128">分析</span><span class="sxs-lookup"><span data-stu-id="a5ff9-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
