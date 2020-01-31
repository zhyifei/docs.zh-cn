---
title: ICorProfilerInfo3::SetFunctionIDMapper2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 107f596801832809e64088c85540c441e66189cf
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868468"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="b753d-102">ICorProfilerInfo3::SetFunctionIDMapper2 方法</span><span class="sxs-lookup"><span data-stu-id="b753d-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="b753d-103">指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。</span><span class="sxs-lookup"><span data-stu-id="b753d-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="b753d-104">此方法将[ICorProfilerInfo：： SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)方法与其他数据参数进行扩展，探查器可能会使用该参数来消除运行时之间的歧义。</span><span class="sxs-lookup"><span data-stu-id="b753d-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b753d-105">语法</span><span class="sxs-lookup"><span data-stu-id="b753d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b753d-106">参数</span><span class="sxs-lookup"><span data-stu-id="b753d-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="b753d-107">中指向[FunctionIDMapper2](functionidmapper2-function.md)实现的指针，将调用该指针以将 `FunctionID` 值映射到其可选值。</span><span class="sxs-lookup"><span data-stu-id="b753d-107">[in] A pointer to a [FunctionIDMapper2](functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="b753d-108">中传递给当前运行时所做的每个[FunctionIDMapper2](functionidmapper2-function.md)函数调用的指针。</span><span class="sxs-lookup"><span data-stu-id="b753d-108">[in] A pointer that is passed to every [FunctionIDMapper2](functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="b753d-109">探查器可使用此信息来消除运行时之间的歧义。</span><span class="sxs-lookup"><span data-stu-id="b753d-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b753d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b753d-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b753d-111">备注</span><span class="sxs-lookup"><span data-stu-id="b753d-111">Remarks</span></span>  
 <span data-ttu-id="b753d-112">FunctionID 值的替代项将传递到探查器的函数入口/出口挂钩（[FunctionEnter3](functionenter3-function.md)、 [FunctionLeave3](functionleave3-function.md)和[FunctionTailcall3](functiontailcall3-function.md) [; 或 FunctionEnter3WithInfo](functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](functionleave3withinfo-function.md)和[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)）（由[SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)或[SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)方法指定）。</span><span class="sxs-lookup"><span data-stu-id="b753d-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md); or [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="b753d-113">`FunctionIDMapper2` 方法只能设置一次;建议你在[ICorProfilerCallback：： Initialize](icorprofilercallback-initialize-method.md)回调中进行设置。</span><span class="sxs-lookup"><span data-stu-id="b753d-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b753d-114">需求</span><span class="sxs-lookup"><span data-stu-id="b753d-114">Requirements</span></span>  
 <span data-ttu-id="b753d-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b753d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b753d-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b753d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b753d-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b753d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b753d-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b753d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b753d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b753d-119">See also</span></span>

- [<span data-ttu-id="b753d-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b753d-120">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="b753d-121">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="b753d-121">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b753d-122">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="b753d-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b753d-123">分析</span><span class="sxs-lookup"><span data-stu-id="b753d-123">Profiling</span></span>](index.md)
