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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 721ee27522b316a561e2f64a322c225cb85a44c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211434"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="444a2-102">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="444a2-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="444a2-103">提供允许代码探查器与公共语言运行时 (CLR) 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。</span><span class="sxs-lookup"><span data-stu-id="444a2-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="444a2-104">方法</span><span class="sxs-lookup"><span data-stu-id="444a2-104">Methods</span></span>  
  
|<span data-ttu-id="444a2-105">方法</span><span class="sxs-lookup"><span data-stu-id="444a2-105">Method</span></span>|<span data-ttu-id="444a2-106">描述</span><span class="sxs-lookup"><span data-stu-id="444a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="444a2-107">SetCodegenFlags 方法</span><span class="sxs-lookup"><span data-stu-id="444a2-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="444a2-108">设置从一个或多个标志[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)枚举来控制代码生成的在实时 (JIT) 重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="444a2-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="444a2-109">SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="444a2-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="444a2-110">替换方法的公共中间语言 (CIL) 主体。</span><span class="sxs-lookup"><span data-stu-id="444a2-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="444a2-111">SetILInstrumentedCodeMap 方法</span><span class="sxs-lookup"><span data-stu-id="444a2-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="444a2-112">使用指定的公共中间语言 (CIL) 映射项为指定的函数设置代码图。</span><span class="sxs-lookup"><span data-stu-id="444a2-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="444a2-113">备注</span><span class="sxs-lookup"><span data-stu-id="444a2-113">Remarks</span></span>  
 <span data-ttu-id="444a2-114">`ICorProfilerFunctionControl` 接口提供了用于控制单个重新编译函数的代码生成的方法。</span><span class="sxs-lookup"><span data-stu-id="444a2-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="444a2-115">探查器获取通过此接口的实例[ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="444a2-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="444a2-116">`ICorProfilerFunctionControl` 的每个实例都可控制一个函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="444a2-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="444a2-117">要求</span><span class="sxs-lookup"><span data-stu-id="444a2-117">Requirements</span></span>  
 <span data-ttu-id="444a2-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="444a2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="444a2-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="444a2-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="444a2-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="444a2-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="444a2-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="444a2-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="444a2-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="444a2-122">See also</span></span>

- [<span data-ttu-id="444a2-123">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="444a2-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="444a2-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="444a2-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="444a2-125">EnumJITedFunctions2 方法</span><span class="sxs-lookup"><span data-stu-id="444a2-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
