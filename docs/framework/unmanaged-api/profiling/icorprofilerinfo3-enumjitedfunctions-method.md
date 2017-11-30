---
title: "ICorProfilerInfo3::EnumJITedFunctions 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.EnumJITedFunctions Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c367ae29cc0daa406356a245f3dc16a671d3c54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="27cf7-102">ICorProfilerInfo3::EnumJITedFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="27cf7-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="27cf7-103">返回已先前 JIT 编译的所有函数的枚举数。</span><span class="sxs-lookup"><span data-stu-id="27cf7-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27cf7-104">语法</span><span class="sxs-lookup"><span data-stu-id="27cf7-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27cf7-105">参数</span><span class="sxs-lookup"><span data-stu-id="27cf7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="27cf7-106">[out]指向的指针[ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)枚举器。</span><span class="sxs-lookup"><span data-stu-id="27cf7-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27cf7-107">备注</span><span class="sxs-lookup"><span data-stu-id="27cf7-107">Remarks</span></span>  
 <span data-ttu-id="27cf7-108">此方法可能会与重叠`JITCompilation`如回调[icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="27cf7-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="27cf7-109">此方法返回的枚举器不包括从使用 Ngen.exe 生成的本机映像加载的函数。</span><span class="sxs-lookup"><span data-stu-id="27cf7-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27cf7-110">返回的枚举包括仅"0"的值的`COR_PRF_FUNCTION::reJitId`字段。</span><span class="sxs-lookup"><span data-stu-id="27cf7-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="27cf7-111">如果你需要有效`COR_PRF_FUNCTION::reJitId`值，请使用[icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="27cf7-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27cf7-112">要求</span><span class="sxs-lookup"><span data-stu-id="27cf7-112">Requirements</span></span>  
 <span data-ttu-id="27cf7-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27cf7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27cf7-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27cf7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27cf7-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27cf7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27cf7-116">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27cf7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27cf7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27cf7-117">See Also</span></span>  
 [<span data-ttu-id="27cf7-118">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="27cf7-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="27cf7-119">分析接口</span><span class="sxs-lookup"><span data-stu-id="27cf7-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="27cf7-120">分析</span><span class="sxs-lookup"><span data-stu-id="27cf7-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
