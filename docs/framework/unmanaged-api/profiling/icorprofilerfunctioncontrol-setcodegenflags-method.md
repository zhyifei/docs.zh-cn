---
title: ICorProfilerFunctionControl::SetCodegenFlags 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 75414ec3d2b30fe8afc5db1e97c81f34b29a3115
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864669"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="9f509-102">ICorProfilerFunctionControl::SetCodegenFlags 方法</span><span class="sxs-lookup"><span data-stu-id="9f509-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="9f509-103">设置[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)枚举中的一个或多个标志，以控制实时（JIT）重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="9f509-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f509-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f509-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f509-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f509-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="9f509-106">中[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)枚举中的一个或多个标志。</span><span class="sxs-lookup"><span data-stu-id="9f509-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f509-107">备注</span><span class="sxs-lookup"><span data-stu-id="9f509-107">Remarks</span></span>  
 <span data-ttu-id="9f509-108">探查器通过[ICorProfilerCallback4：： GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)回调获取此接口的实例。</span><span class="sxs-lookup"><span data-stu-id="9f509-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="9f509-109">`SetCodegenFlags` 允许探查器控制重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="9f509-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="9f509-110">与所有其他 JIT 重新编译参数一样，代码生成标志适用于函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="9f509-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="9f509-111">编译函数时，JIT 编译器会将这些编译标志连同其他源指定的其他标志一起考虑。</span><span class="sxs-lookup"><span data-stu-id="9f509-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="9f509-112">其他源包括调试器、启动时探查器设置的全局标志 `COR_PRF_DISABLE_OPTIMIZATIONS``COR_PRF_DISABLE_INLINING` （使用[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)方法）、探查器的[ICorProfilerCallback：： JITInlining](icorprofilercallback-jitinlining-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="9f509-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="9f509-113">JIT 编译器为请求最小优化量的源提供优先级别。</span><span class="sxs-lookup"><span data-stu-id="9f509-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="9f509-114">例如，如果探查器在启动时指定了 `COR_PRF_DISABLE_INLINING`，但没有在[ICorProfilerFunctionControl：： SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)回调中指定 `COR_PRF_CODEGEN_DISABLE_INLINING`，则仍将禁用内联。</span><span class="sxs-lookup"><span data-stu-id="9f509-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="9f509-115">同样，如果探查器未在 `SetCodegenFlags`中指定 `COR_PRF_CODEGEN_DISABLE_INLINING`，而是通过使用[ICorProfilerCallback：： JITInlining](icorprofilercallback-jitinlining-method.md)回调禁用内联，则禁用内联。</span><span class="sxs-lookup"><span data-stu-id="9f509-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f509-116">需求</span><span class="sxs-lookup"><span data-stu-id="9f509-116">Requirements</span></span>  
 <span data-ttu-id="9f509-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f509-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f509-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f509-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f509-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f509-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f509-120">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f509-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f509-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f509-121">See also</span></span>

- [<span data-ttu-id="9f509-122">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="9f509-122">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
