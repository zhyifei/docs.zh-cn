---
title: "ICorProfilerInfo::GetFunctionInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17512077ef7a8ca45fa76c00f93612015948d083
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="2713d-102">ICorProfilerInfo::GetFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="2713d-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="2713d-103">获取父类和元数据标记指定的函数。</span><span class="sxs-lookup"><span data-stu-id="2713d-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2713d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2713d-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2713d-105">参数</span><span class="sxs-lookup"><span data-stu-id="2713d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2713d-106">[in]要为其获取令牌的父类和元数据函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="2713d-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="2713d-107">[out] 一个指向函数的父类的指针。</span><span class="sxs-lookup"><span data-stu-id="2713d-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="2713d-108">[out] 一个指向在其中定义函数父类的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="2713d-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="2713d-109">[out] 指向函数的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="2713d-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2713d-110">备注</span><span class="sxs-lookup"><span data-stu-id="2713d-110">Remarks</span></span>  
 <span data-ttu-id="2713d-111">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)以获取给定模块的元数据接口。</span><span class="sxs-lookup"><span data-stu-id="2713d-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="2713d-112">然后，返回到 `pToken` 所引用位置的元数据标记便可用于访问该函数的元数据。</span><span class="sxs-lookup"><span data-stu-id="2713d-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="2713d-113">`ClassID`泛型类的函数可能无法获得不包含有关使用的函数的更多上下文的信息。</span><span class="sxs-lookup"><span data-stu-id="2713d-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="2713d-114">在这种情况下，`pClassId`将为 0。</span><span class="sxs-lookup"><span data-stu-id="2713d-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="2713d-115">探查器代码应使用[icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) COR_PRF_FRAME_INFO 值以提供更多上下文。</span><span class="sxs-lookup"><span data-stu-id="2713d-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2713d-116">惠?</span><span class="sxs-lookup"><span data-stu-id="2713d-116">Requirements</span></span>  
 <span data-ttu-id="2713d-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2713d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2713d-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2713d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2713d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2713d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2713d-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2713d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2713d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2713d-121">See Also</span></span>  
 [<span data-ttu-id="2713d-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="2713d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
