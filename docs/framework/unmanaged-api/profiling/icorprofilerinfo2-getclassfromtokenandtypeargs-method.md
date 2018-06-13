---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04be252092732296354cfec102cf8fe648ed2dd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456633"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="6ede5-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 方法</span><span class="sxs-lookup"><span data-stu-id="6ede5-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="6ede5-103">获取`ClassID`通过使用指定元数据标记的类型和`ClassID`值的任何类型参数。</span><span class="sxs-lookup"><span data-stu-id="6ede5-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ede5-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ede5-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ede5-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ede5-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6ede5-106">[in]该类型所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="6ede5-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="6ede5-107">[in]`mdTypeDef`引用该类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="6ede5-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="6ede5-108">[in]对于给定的类型的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="6ede5-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="6ede5-109">此值必须为非泛型类型的零。</span><span class="sxs-lookup"><span data-stu-id="6ede5-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="6ede5-110">[in]数组`ClassID`值，其中每个是类型的自变量。</span><span class="sxs-lookup"><span data-stu-id="6ede5-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="6ede5-111">值`typeArgs`时可以为 NULL`cTypeArgs`设置为零。</span><span class="sxs-lookup"><span data-stu-id="6ede5-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="6ede5-112">[out]一个指向`ClassID`的指定类型。</span><span class="sxs-lookup"><span data-stu-id="6ede5-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ede5-113">备注</span><span class="sxs-lookup"><span data-stu-id="6ede5-113">Remarks</span></span>  
 <span data-ttu-id="6ede5-114">调用`GetClassFromTokenAndTypeArgs`方法替换`mdTypeRef`而不是`mdTypeDef`元数据的令牌可以具有不可预知的结果; 调用方应解决`mdTypeRef`到`mdTypeDef`时将其传递。</span><span class="sxs-lookup"><span data-stu-id="6ede5-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="6ede5-115">如果尚未加载该类型，则调用`GetClassFromTokenAndTypeArgs`将触发加载，这是一种危险操作在多种上下文中的。</span><span class="sxs-lookup"><span data-stu-id="6ede5-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="6ede5-116">例如，在模块或其他类型的加载过程中调用此方法在运行时尝试循环加载某些内容导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="6ede5-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="6ede5-117">一般情况下，使用`GetClassFromTokenAndTypeArgs`不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="6ede5-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="6ede5-118">如果探查器感兴趣的特定类型的事件，它们应将存储`ModuleID`和`mdTypeDef`该类型，并使用[icorprofilerinfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)以检查是否给定`ClassID`是所需的类型。</span><span class="sxs-lookup"><span data-stu-id="6ede5-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ede5-119">要求</span><span class="sxs-lookup"><span data-stu-id="6ede5-119">Requirements</span></span>  
 <span data-ttu-id="6ede5-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ede5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ede5-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ede5-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ede5-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ede5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ede5-123">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ede5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ede5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ede5-124">See Also</span></span>  
 [<span data-ttu-id="6ede5-125">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6ede5-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="6ede5-126">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="6ede5-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
