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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 343cedcf26112f0f2bcc7943ea5ee9f302329a15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457472"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="e67b1-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 方法</span><span class="sxs-lookup"><span data-stu-id="e67b1-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="e67b1-103">获取`FunctionID`通过使用指定元数据标记，包含类的函数和`ClassID`值的任何类型参数。</span><span class="sxs-lookup"><span data-stu-id="e67b1-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="e67b1-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e67b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="e67b1-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="e67b1-106">[in]函数所在模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="e67b1-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="e67b1-107">[in]`mdMethodDef`引用该函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e67b1-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="e67b1-108">[in]函数的包含类的 ID。</span><span class="sxs-lookup"><span data-stu-id="e67b1-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="e67b1-109">[in]给定的函数的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="e67b1-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="e67b1-110">此值必须为零的非泛型函数。</span><span class="sxs-lookup"><span data-stu-id="e67b1-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="e67b1-111">[in]数组`ClassID`值，其中每个是函数的自变量。</span><span class="sxs-lookup"><span data-stu-id="e67b1-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="e67b1-112">值`typeArgs`时可以为 NULL`cTypeArgs`设置为零。</span><span class="sxs-lookup"><span data-stu-id="e67b1-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="e67b1-113">[out]指向的指针`FunctionID`指定函数。</span><span class="sxs-lookup"><span data-stu-id="e67b1-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e67b1-114">备注</span><span class="sxs-lookup"><span data-stu-id="e67b1-114">Remarks</span></span>  
 <span data-ttu-id="e67b1-115">调用`GetFunctionFromTokenAndTypeArgs`方法替换`mdMethodRef`元数据，而不是`mdMethodDef`元数据的令牌可以具有不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="e67b1-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="e67b1-116">调用方应解决`mdMethodRef`到`mdMethodDef`时将其传递。</span><span class="sxs-lookup"><span data-stu-id="e67b1-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="e67b1-117">如果尚未加载该函数，则调用`GetFunctionFromTokenAndTypeArgs`将导致加载发生，这是一种危险操作在多种上下文中的。</span><span class="sxs-lookup"><span data-stu-id="e67b1-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="e67b1-118">例如，在模块或类型的加载过程中调用此方法在运行时尝试循环加载某些内容导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="e67b1-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="e67b1-119">一般情况下，使用`GetFunctionFromTokenAndTypeArgs`不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="e67b1-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="e67b1-120">如果探查器感兴趣的特定函数的事件，它们应将存储`ModuleID`和`mdMethodDef`该函数，并使用[icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)以检查是否给定`FunctionID`是所需的函数。</span><span class="sxs-lookup"><span data-stu-id="e67b1-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e67b1-121">要求</span><span class="sxs-lookup"><span data-stu-id="e67b1-121">Requirements</span></span>  
 <span data-ttu-id="e67b1-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e67b1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67b1-123">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e67b1-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e67b1-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e67b1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e67b1-125">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e67b1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67b1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e67b1-126">See Also</span></span>  
 [<span data-ttu-id="e67b1-127">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e67b1-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="e67b1-128">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="e67b1-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
