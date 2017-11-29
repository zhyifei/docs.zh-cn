---
title: "ICorProfilerInfo2::GetClassIDInfo2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassIDInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8bfa970acd21a518112dd6ee9228b621758e49f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="bc82f-102">ICorProfilerInfo2::GetClassIDInfo2 方法</span><span class="sxs-lookup"><span data-stu-id="bc82f-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="bc82f-103">打开泛型定义中指定的类中，令牌获取的父模块和元数据`ClassID`其父类和`ClassID`每个类型参数，（如果存在） 的类。</span><span class="sxs-lookup"><span data-stu-id="bc82f-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc82f-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc82f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="bc82f-105">参数</span><span class="sxs-lookup"><span data-stu-id="bc82f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="bc82f-106">[in] 将为其检索信息的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="bc82f-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="bc82f-107">[out]打开泛型定义中指定的类的父模块 id 的指针。</span><span class="sxs-lookup"><span data-stu-id="bc82f-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="bc82f-108">[out]打开泛型定义中指定的类的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="bc82f-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="bc82f-109">[out] 指向父类 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="bc82f-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="bc82f-110">[in] `typeArgs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="bc82f-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="bc82f-111">[out] 指向可用元素总数的指针。</span><span class="sxs-lookup"><span data-stu-id="bc82f-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="bc82f-112">[out] `ClassID` 值的数组，其中每个值表示类的类型参数 ID。</span><span class="sxs-lookup"><span data-stu-id="bc82f-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="bc82f-113">方法返回时，`typeArgs` 将包含部分或全部可用 `ClassID` 值。</span><span class="sxs-lookup"><span data-stu-id="bc82f-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc82f-114">备注</span><span class="sxs-lookup"><span data-stu-id="bc82f-114">Remarks</span></span>  
 <span data-ttu-id="bc82f-115">`GetClassIDInfo2`方法类似于是[icorprofilerinfo:: Getclassidinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)方法，但`GetClassIDInfo2`包含有关泛型类型的其他信息。</span><span class="sxs-lookup"><span data-stu-id="bc82f-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="bc82f-116">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)获取[元数据](../../../../docs/framework/unmanaged-api/metadata/index.md)给定模块的接口。</span><span class="sxs-lookup"><span data-stu-id="bc82f-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="bc82f-117">返回至 `pTypeDefToken` 所引用的位置的元数据标记可用于访问类的元数据。</span><span class="sxs-lookup"><span data-stu-id="bc82f-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="bc82f-118">`GetClassIDInfo2` 返回后，必须验证 `typeArgs` 缓冲区是否足够大，可包含所有 `ClassID` 值。</span><span class="sxs-lookup"><span data-stu-id="bc82f-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="bc82f-119">为此，请比较 `pcNumTypeArgs` 指向的值和 `cNumTypeArgs` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="bc82f-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="bc82f-120">如果 `pcNumTypeArgs` 指向的值大于 `cNumTypeArgs`，请分配更大的 `typeArgs` 缓冲区，并用新的、更大的大小更新 `cNumTypeArgs`，然后再次调用 `GetClassIDInfo2`。</span><span class="sxs-lookup"><span data-stu-id="bc82f-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="bc82f-121">或者，可以先用长度为零的 `typeArgs` 缓冲区调用 `GetClassIDInfo2` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="bc82f-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="bc82f-122">然后，可将 `typeArgs` 缓冲区大小设置为 `pcNumTypeArgs` 中返回的值，并再次调用 `GetClassIDInfo2`。</span><span class="sxs-lookup"><span data-stu-id="bc82f-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc82f-123">要求</span><span class="sxs-lookup"><span data-stu-id="bc82f-123">Requirements</span></span>  
 <span data-ttu-id="bc82f-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc82f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc82f-125">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc82f-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc82f-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc82f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc82f-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc82f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc82f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc82f-128">See Also</span></span>  
 [<span data-ttu-id="bc82f-129">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="bc82f-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="bc82f-130">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="bc82f-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="bc82f-131">分析接口</span><span class="sxs-lookup"><span data-stu-id="bc82f-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="bc82f-132">分析</span><span class="sxs-lookup"><span data-stu-id="bc82f-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
