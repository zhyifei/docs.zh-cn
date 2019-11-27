---
title: ICorProfilerCallback4::GetReJITParameters 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439436"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="566e6-102">ICorProfilerCallback4::GetReJITParameters 方法</span><span class="sxs-lookup"><span data-stu-id="566e6-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="566e6-103">允许代码探查器为新的重新编译的方法体设置备用代码生成标志。</span><span class="sxs-lookup"><span data-stu-id="566e6-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="566e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="566e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="566e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="566e6-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="566e6-106">中包含 CLR 需要 JIT 重新编译参数的方法的模块。</span><span class="sxs-lookup"><span data-stu-id="566e6-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="566e6-107">中CLR 需要 JIT 重新编译参数的方法的 `MethodDef`。</span><span class="sxs-lookup"><span data-stu-id="566e6-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="566e6-108">中指向[ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)接口的指针，探查器可以使用该接口为要重新编译的方法提供 JIT 重新编译信息。</span><span class="sxs-lookup"><span data-stu-id="566e6-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="566e6-109">备注</span><span class="sxs-lookup"><span data-stu-id="566e6-109">Remarks</span></span>  
 <span data-ttu-id="566e6-110">CLR 发出 `GetReJITParameters` 回调，以便探查器可以指定用于重新编译给定方法的参数。</span><span class="sxs-lookup"><span data-stu-id="566e6-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="566e6-111">每个函数只发出一次 `GetReJITParameters` 回调;探查器提供的参数适用于该函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="566e6-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="566e6-112">要求</span><span class="sxs-lookup"><span data-stu-id="566e6-112">Requirements</span></span>  
 <span data-ttu-id="566e6-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="566e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="566e6-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="566e6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="566e6-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="566e6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="566e6-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="566e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="566e6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="566e6-117">See also</span></span>

- [<span data-ttu-id="566e6-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="566e6-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="566e6-119">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="566e6-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="566e6-120">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="566e6-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="566e6-121">ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="566e6-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
