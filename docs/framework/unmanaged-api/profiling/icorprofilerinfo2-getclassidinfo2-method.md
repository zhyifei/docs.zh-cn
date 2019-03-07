---
title: ICorProfilerInfo2::GetClassIDInfo2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d58174aa8b8d0e0544566faa6b1d79c2c3d6197
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472611"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="06a91-102">ICorProfilerInfo2::GetClassIDInfo2 方法</span><span class="sxs-lookup"><span data-stu-id="06a91-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="06a91-103">获取父模块和元数据标记为开放泛型定义中指定类的`ClassID`其父类和`ClassID`为每个类型参数时，如果存在的类。</span><span class="sxs-lookup"><span data-stu-id="06a91-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a91-104">语法</span><span class="sxs-lookup"><span data-stu-id="06a91-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06a91-105">参数</span><span class="sxs-lookup"><span data-stu-id="06a91-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="06a91-106">[in] 将为其检索信息的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="06a91-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="06a91-107">[out]为开放泛型定义中指定的类的父模块 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="06a91-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="06a91-108">[out]为开放泛型定义中的指定类的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="06a91-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="06a91-109">[out] 指向父类 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="06a91-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="06a91-110">[in] `typeArgs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="06a91-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="06a91-111">[out] 指向可用元素总数的指针。</span><span class="sxs-lookup"><span data-stu-id="06a91-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="06a91-112">[out] `ClassID` 值的数组，其中每个值表示类的类型参数 ID。</span><span class="sxs-lookup"><span data-stu-id="06a91-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="06a91-113">方法返回时，`typeArgs` 将包含部分或全部可用 `ClassID` 值。</span><span class="sxs-lookup"><span data-stu-id="06a91-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06a91-114">备注</span><span class="sxs-lookup"><span data-stu-id="06a91-114">Remarks</span></span>  
 <span data-ttu-id="06a91-115">`GetClassIDInfo2`方法是类似于[icorprofilerinfo:: Getclassidinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)方法，但`GetClassIDInfo2`获取有关泛型类型的其他信息。</span><span class="sxs-lookup"><span data-stu-id="06a91-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="06a91-116">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)来获取[元数据](../../../../docs/framework/unmanaged-api/metadata/index.md)给定模块的接口。</span><span class="sxs-lookup"><span data-stu-id="06a91-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="06a91-117">返回至 `pTypeDefToken` 所引用的位置的元数据标记可用于访问类的元数据。</span><span class="sxs-lookup"><span data-stu-id="06a91-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="06a91-118">`GetClassIDInfo2` 返回后，必须验证 `typeArgs` 缓冲区是否足够大，可包含所有 `ClassID` 值。</span><span class="sxs-lookup"><span data-stu-id="06a91-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="06a91-119">为此，请比较 `pcNumTypeArgs` 指向的值和 `cNumTypeArgs` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="06a91-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="06a91-120">如果 `pcNumTypeArgs` 指向的值大于 `cNumTypeArgs`，请分配更大的 `typeArgs` 缓冲区，并用新的、更大的大小更新 `cNumTypeArgs`，然后再次调用 `GetClassIDInfo2`。</span><span class="sxs-lookup"><span data-stu-id="06a91-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="06a91-121">或者，可以先用长度为零的 `typeArgs` 缓冲区调用 `GetClassIDInfo2` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="06a91-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="06a91-122">然后，可将 `typeArgs` 缓冲区大小设置为 `pcNumTypeArgs` 中返回的值，并再次调用 `GetClassIDInfo2`。</span><span class="sxs-lookup"><span data-stu-id="06a91-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06a91-123">要求</span><span class="sxs-lookup"><span data-stu-id="06a91-123">Requirements</span></span>  
 <span data-ttu-id="06a91-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06a91-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a91-125">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06a91-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06a91-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06a91-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06a91-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a91-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a91-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="06a91-128">See also</span></span>
- [<span data-ttu-id="06a91-129">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="06a91-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="06a91-130">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="06a91-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="06a91-131">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="06a91-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="06a91-132">分析</span><span class="sxs-lookup"><span data-stu-id="06a91-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
