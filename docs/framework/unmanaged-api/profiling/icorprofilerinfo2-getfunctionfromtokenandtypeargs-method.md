---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433208"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="c0479-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 方法</span><span class="sxs-lookup"><span data-stu-id="c0479-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="c0479-103">使用指定的元数据标记（包含类）和任何类型参数 `ClassID` 值获取函数的 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="c0479-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0479-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0479-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0479-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0479-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c0479-106">中函数所在模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="c0479-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="c0479-107">中引用函数的 `mdMethodDef` 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c0479-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="c0479-108">中函数的包含类的 ID。</span><span class="sxs-lookup"><span data-stu-id="c0479-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c0479-109">中给定函数的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="c0479-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="c0479-110">对于非泛型函数，此值必须为零。</span><span class="sxs-lookup"><span data-stu-id="c0479-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c0479-111">中`ClassID` 值的数组，其中每个值都是函数的参数。</span><span class="sxs-lookup"><span data-stu-id="c0479-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="c0479-112">如果 `cTypeArgs` 设置为零，则 `typeArgs` 的值可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c0479-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="c0479-113">弄指向指定函数的 `FunctionID` 的指针。</span><span class="sxs-lookup"><span data-stu-id="c0479-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0479-114">备注</span><span class="sxs-lookup"><span data-stu-id="c0479-114">Remarks</span></span>  
 <span data-ttu-id="c0479-115">使用 `mdMethodRef` 元数据而不是 `mdMethodDef` 元数据令牌调用 `GetFunctionFromTokenAndTypeArgs` 方法可能会产生不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="c0479-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="c0479-116">调用方应在传递时将 `mdMethodRef` 解析为 `mdMethodDef`。</span><span class="sxs-lookup"><span data-stu-id="c0479-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="c0479-117">如果尚未加载该函数，则调用 `GetFunctionFromTokenAndTypeArgs` 将导致加载，这在许多上下文中是一个危险操作。</span><span class="sxs-lookup"><span data-stu-id="c0479-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="c0479-118">例如，在模块或类型加载过程中调用此方法可能会导致无限循环，因为运行时尝试循环加载某些功能。</span><span class="sxs-lookup"><span data-stu-id="c0479-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="c0479-119">通常，不建议使用 `GetFunctionFromTokenAndTypeArgs`。</span><span class="sxs-lookup"><span data-stu-id="c0479-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="c0479-120">如果探查器对特定函数的事件感兴趣，则它们应存储该函数的 `ModuleID` 和 `mdMethodDef`，并使用[ICorProfilerInfo2：： GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)来检查给定的 `FunctionID` 是否为所需函数的。</span><span class="sxs-lookup"><span data-stu-id="c0479-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0479-121">要求</span><span class="sxs-lookup"><span data-stu-id="c0479-121">Requirements</span></span>  
 <span data-ttu-id="c0479-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0479-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0479-123">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0479-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0479-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0479-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0479-125">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0479-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0479-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0479-126">See also</span></span>

- [<span data-ttu-id="c0479-127">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c0479-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c0479-128">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="c0479-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
