---
title: ICorProfilerFunctionControl 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 1286ce953c96eb3e3164ba5b209031dd1ec5c453
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864688"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="36919-102">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="36919-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="36919-103">提供允许代码探查器与公共语言运行时 (CLR) 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。</span><span class="sxs-lookup"><span data-stu-id="36919-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36919-104">方法</span><span class="sxs-lookup"><span data-stu-id="36919-104">Methods</span></span>  
  
|<span data-ttu-id="36919-105">方法</span><span class="sxs-lookup"><span data-stu-id="36919-105">Method</span></span>|<span data-ttu-id="36919-106">描述</span><span class="sxs-lookup"><span data-stu-id="36919-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36919-107">SetCodegenFlags 方法</span><span class="sxs-lookup"><span data-stu-id="36919-107">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="36919-108">设置[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)枚举中的一个或多个标志，以控制实时（JIT）重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="36919-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="36919-109">SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="36919-109">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="36919-110">替换方法的公共中间语言 (CIL) 主体。</span><span class="sxs-lookup"><span data-stu-id="36919-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="36919-111">SetILInstrumentedCodeMap 方法</span><span class="sxs-lookup"><span data-stu-id="36919-111">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="36919-112">使用指定的公共中间语言 (CIL) 映射项为指定的函数设置代码图。</span><span class="sxs-lookup"><span data-stu-id="36919-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36919-113">备注</span><span class="sxs-lookup"><span data-stu-id="36919-113">Remarks</span></span>  
 <span data-ttu-id="36919-114">`ICorProfilerFunctionControl` 接口提供了用于控制单个重新编译函数的代码生成的方法。</span><span class="sxs-lookup"><span data-stu-id="36919-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="36919-115">探查器通过[ICorProfilerCallback4：： GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)回调获取此接口的实例。</span><span class="sxs-lookup"><span data-stu-id="36919-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="36919-116">`ICorProfilerFunctionControl` 的每个实例都可控制一个函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="36919-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36919-117">需求</span><span class="sxs-lookup"><span data-stu-id="36919-117">Requirements</span></span>  
 <span data-ttu-id="36919-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36919-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36919-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36919-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36919-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36919-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36919-121">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36919-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36919-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36919-122">See also</span></span>

- [<span data-ttu-id="36919-123">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="36919-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="36919-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="36919-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="36919-125">EnumJITedFunctions2 方法</span><span class="sxs-lookup"><span data-stu-id="36919-125">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
