---
title: "ICorProfilerFunctionControl 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl
helpviewer_keywords: ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09a0a839c9cd69c7926c19cceffc56ee928f2f02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="a02a7-102">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="a02a7-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="a02a7-103">提供允许代码探查器与公共语言运行时 (CLR) 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。</span><span class="sxs-lookup"><span data-stu-id="a02a7-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a02a7-104">方法</span><span class="sxs-lookup"><span data-stu-id="a02a7-104">Methods</span></span>  
  
|<span data-ttu-id="a02a7-105">方法</span><span class="sxs-lookup"><span data-stu-id="a02a7-105">Method</span></span>|<span data-ttu-id="a02a7-106">描述</span><span class="sxs-lookup"><span data-stu-id="a02a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a02a7-107">SetCodegenFlags 方法</span><span class="sxs-lookup"><span data-stu-id="a02a7-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="a02a7-108">设置从一个或多个标志[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)枚举控制代码生成中实时 (JIT) 重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="a02a7-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="a02a7-109">SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="a02a7-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="a02a7-110">替换方法的公共中间语言 (CIL) 主体。</span><span class="sxs-lookup"><span data-stu-id="a02a7-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="a02a7-111">SetILInstrumentedCodeMap 方法</span><span class="sxs-lookup"><span data-stu-id="a02a7-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="a02a7-112">使用指定的公共中间语言 (CIL) 映射项为指定的函数设置代码图。</span><span class="sxs-lookup"><span data-stu-id="a02a7-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a02a7-113">备注</span><span class="sxs-lookup"><span data-stu-id="a02a7-113">Remarks</span></span>  
 <span data-ttu-id="a02a7-114">`ICorProfilerFunctionControl` 接口提供了用于控制单个重新编译函数的代码生成的方法。</span><span class="sxs-lookup"><span data-stu-id="a02a7-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="a02a7-115">探查器获取通过此接口的实例[icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="a02a7-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="a02a7-116">`ICorProfilerFunctionControl` 的每个实例都可控制一个函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="a02a7-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a02a7-117">要求</span><span class="sxs-lookup"><span data-stu-id="a02a7-117">Requirements</span></span>  
 <span data-ttu-id="a02a7-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a02a7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a02a7-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a02a7-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a02a7-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a02a7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a02a7-121">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a02a7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a02a7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a02a7-122">See Also</span></span>  
 [<span data-ttu-id="a02a7-123">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="a02a7-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="a02a7-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="a02a7-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="a02a7-125">EnumJITedFunctions2 方法</span><span class="sxs-lookup"><span data-stu-id="a02a7-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
