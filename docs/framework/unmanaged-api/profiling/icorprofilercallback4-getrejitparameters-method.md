---
title: "ICorProfilerCallback4::GetReJITParameters 方法"
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
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03e5440fbd016f52642a5626b0cf0b82e7ecea45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="7a8f1-102">ICorProfilerCallback4::GetReJITParameters 方法</span><span class="sxs-lookup"><span data-stu-id="7a8f1-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="7a8f1-103">允许代码探查器设置新的重新编译的方法体的替代代码生成标志。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a8f1-104">Syntax</span></span>  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a8f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a8f1-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="7a8f1-106">[in]包含 CLR 需要 JIT 重新编译参数的方法的模块。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="7a8f1-107">[in]`MethodDef` CLR 需要 JIT 重新编译参数的方法。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="7a8f1-108">[in]指向的指针[ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)探查器可用于提供有关正在重新编译的方法的 JIT 重新编译信息的接口。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a8f1-109">备注</span><span class="sxs-lookup"><span data-stu-id="7a8f1-109">Remarks</span></span>  
 <span data-ttu-id="7a8f1-110">CLR 问题`GetReJITParameters`回调，这样探查器可以指定重新编译给定的方法的参数。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="7a8f1-111">`GetReJITParameters`回调会发出仅一次每个函数; 由探查器提供的参数适用于该函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8f1-112">惠?</span><span class="sxs-lookup"><span data-stu-id="7a8f1-112">Requirements</span></span>  
 <span data-ttu-id="7a8f1-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a8f1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8f1-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a8f1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a8f1-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a8f1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a8f1-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a8f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8f1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a8f1-117">See Also</span></span>  
 [<span data-ttu-id="7a8f1-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7a8f1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="7a8f1-119">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="7a8f1-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="7a8f1-120">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="7a8f1-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="7a8f1-121">ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="7a8f1-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
