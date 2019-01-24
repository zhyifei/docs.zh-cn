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
ms.openlocfilehash: 0651609e6d2597336ee42ceae752df7e561cd252
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692647"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="fb960-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 方法</span><span class="sxs-lookup"><span data-stu-id="fb960-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="fb960-103">获取`ClassID`通过使用指定的元数据标记的类型和`ClassID`的任何值类型参数。</span><span class="sxs-lookup"><span data-stu-id="fb960-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb960-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb960-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb960-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb960-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="fb960-106">[in]该类型所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="fb960-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="fb960-107">[in]`mdTypeDef`元数据标记所引用的类型。</span><span class="sxs-lookup"><span data-stu-id="fb960-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="fb960-108">[in]为给定类型的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="fb960-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="fb960-109">此值必须为零的非泛型类型。</span><span class="sxs-lookup"><span data-stu-id="fb960-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="fb960-110">[in]一个数组`ClassID`值，其中每个类型的自变量。</span><span class="sxs-lookup"><span data-stu-id="fb960-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="fb960-111">值`typeArgs`可以为 NULL，如果`cTypeArgs`设置为零。</span><span class="sxs-lookup"><span data-stu-id="fb960-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="fb960-112">[out]一个指向`ClassID`的指定类型。</span><span class="sxs-lookup"><span data-stu-id="fb960-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb960-113">备注</span><span class="sxs-lookup"><span data-stu-id="fb960-113">Remarks</span></span>  
 <span data-ttu-id="fb960-114">调用`GetClassFromTokenAndTypeArgs`方法替换`mdTypeRef`而不是`mdTypeDef`元数据标记可以具有不可预知的结果; 调用方应解决`mdTypeRef`到`mdTypeDef`时将其传递。</span><span class="sxs-lookup"><span data-stu-id="fb960-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="fb960-115">如果尚未加载该类型，则调用`GetClassFromTokenAndTypeArgs`将触发加载，这是一种危险操作在多种上下文中的。</span><span class="sxs-lookup"><span data-stu-id="fb960-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="fb960-116">例如，在模块或其他类型的加载过程中调用此方法在运行时尝试循环加载某些内容导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="fb960-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="fb960-117">一般情况下，使用`GetClassFromTokenAndTypeArgs`不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="fb960-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="fb960-118">如果探查器感兴趣的特定类型的事件，它们应存储`ModuleID`并`mdTypeDef`的该类型，以及使用[ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)若要检查是否给定`ClassID`是所需的类型。</span><span class="sxs-lookup"><span data-stu-id="fb960-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb960-119">要求</span><span class="sxs-lookup"><span data-stu-id="fb960-119">Requirements</span></span>  
 <span data-ttu-id="fb960-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb960-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb960-121">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb960-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb960-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb960-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb960-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb960-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb960-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb960-124">See also</span></span>
- [<span data-ttu-id="fb960-125">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="fb960-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="fb960-126">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="fb960-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
