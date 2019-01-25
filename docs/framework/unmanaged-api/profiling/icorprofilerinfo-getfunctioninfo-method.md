---
title: ICorProfilerInfo::GetFunctionInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00b20134c0134aa30d2056b634c8525f66ed8cf5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602451"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="5cf8d-102">ICorProfilerInfo::GetFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5cf8d-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="5cf8d-103">获取父类和元数据令牌指定的函数。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cf8d-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cf8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cf8d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5cf8d-106">[in]若要获取的父类和元数据令牌的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="5cf8d-107">[out] 一个指向函数的父类的指针。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="5cf8d-108">[out] 一个指向在其中定义函数父类的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="5cf8d-109">[out] 指向函数的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cf8d-110">备注</span><span class="sxs-lookup"><span data-stu-id="5cf8d-110">Remarks</span></span>  
 <span data-ttu-id="5cf8d-111">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)以获取给定模块的元数据接口。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="5cf8d-112">然后，返回到 `pToken` 所引用位置的元数据标记便可用于访问该函数的元数据。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="5cf8d-113">`ClassID`的泛型类的一个函数可能无法获得而无需使用有关的函数的更多上下文的信息。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="5cf8d-114">在这种情况下，`pClassId`将为 0。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="5cf8d-115">Profiler 的代码应使用[ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) COR_PRF_FRAME_INFO 值以提供更多上下文。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cf8d-116">要求</span><span class="sxs-lookup"><span data-stu-id="5cf8d-116">Requirements</span></span>  
 <span data-ttu-id="5cf8d-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5cf8d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf8d-118">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5cf8d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5cf8d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cf8d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cf8d-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf8d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf8d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cf8d-121">See also</span></span>
- [<span data-ttu-id="5cf8d-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5cf8d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
