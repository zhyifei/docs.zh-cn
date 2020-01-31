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
ms.openlocfilehash: 823cc5638ff3e0955aca0bd9ba5795f6b369c6b0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863603"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="fabf1-102">ICorProfilerInfo::GetFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="fabf1-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="fabf1-103">获取指定函数的父类和元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fabf1-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fabf1-104">语法</span><span class="sxs-lookup"><span data-stu-id="fabf1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fabf1-105">参数</span><span class="sxs-lookup"><span data-stu-id="fabf1-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fabf1-106">中要获取其父类和元数据标记的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="fabf1-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="fabf1-107">[out] 一个指向函数的父类的指针。</span><span class="sxs-lookup"><span data-stu-id="fabf1-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="fabf1-108">[out] 一个指向在其中定义函数父类的模块的指针。</span><span class="sxs-lookup"><span data-stu-id="fabf1-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="fabf1-109">[out] 指向函数的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="fabf1-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fabf1-110">备注</span><span class="sxs-lookup"><span data-stu-id="fabf1-110">Remarks</span></span>  
 <span data-ttu-id="fabf1-111">探查器代码可调用[ICorProfilerInfo：： GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md)以获取给定模块的元数据接口。</span><span class="sxs-lookup"><span data-stu-id="fabf1-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="fabf1-112">然后，返回到 `pToken` 所引用位置的元数据标记便可用于访问该函数的元数据。</span><span class="sxs-lookup"><span data-stu-id="fabf1-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="fabf1-113">在泛型类上执行函数的 `ClassID` 可能无法获得有关函数使用的更多上下文信息。</span><span class="sxs-lookup"><span data-stu-id="fabf1-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="fabf1-114">在这种情况下，`pClassId` 将为0。</span><span class="sxs-lookup"><span data-stu-id="fabf1-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="fabf1-115">探查器代码应将[ICorProfilerInfo2：： GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)与 COR_PRF_FRAME_INFO 值一起使用，以提供更多上下文。</span><span class="sxs-lookup"><span data-stu-id="fabf1-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fabf1-116">需求</span><span class="sxs-lookup"><span data-stu-id="fabf1-116">Requirements</span></span>  
 <span data-ttu-id="fabf1-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fabf1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fabf1-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fabf1-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fabf1-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fabf1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fabf1-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fabf1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabf1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fabf1-121">See also</span></span>

- [<span data-ttu-id="fabf1-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="fabf1-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
