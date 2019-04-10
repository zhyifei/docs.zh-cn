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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d04c15fa181d0e7bf8a92c1b6ecdef5b8b13bd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182424"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="463ec-102">ICorProfilerInfo3::SetFunctionIDMapper2 方法</span><span class="sxs-lookup"><span data-stu-id="463ec-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="463ec-103">指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。</span><span class="sxs-lookup"><span data-stu-id="463ec-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="463ec-104">此方法扩展[icorprofilerinfo:: Setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)与探查器可能用于消除运行时间歧义一个额外的数据参数的方法。</span><span class="sxs-lookup"><span data-stu-id="463ec-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="463ec-105">语法</span><span class="sxs-lookup"><span data-stu-id="463ec-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="463ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="463ec-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="463ec-107">[in]一个指向[FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)实现，它将调用映射`FunctionID`为其替代值的值。</span><span class="sxs-lookup"><span data-stu-id="463ec-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="463ec-108">[in]一个指针，它传递到每个[FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)函数所做的当前运行时调用。</span><span class="sxs-lookup"><span data-stu-id="463ec-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="463ec-109">探查器可以使用此信息来区分运行时。</span><span class="sxs-lookup"><span data-stu-id="463ec-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="463ec-110">返回值</span><span class="sxs-lookup"><span data-stu-id="463ec-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="463ec-111">备注</span><span class="sxs-lookup"><span data-stu-id="463ec-111">Remarks</span></span>  
 <span data-ttu-id="463ec-112">FunctionID 值备选方法将传递给探查器的输入/退出挂钩函数 ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，并[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md);或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，并[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) 由指定的[SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)或[SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="463ec-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="463ec-113">`FunctionIDMapper2`方法可以进行一次设置，我们建议将其设置[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="463ec-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="463ec-114">要求</span><span class="sxs-lookup"><span data-stu-id="463ec-114">Requirements</span></span>  
 <span data-ttu-id="463ec-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="463ec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="463ec-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="463ec-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="463ec-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="463ec-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="463ec-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="463ec-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="463ec-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="463ec-119">See also</span></span>

- [<span data-ttu-id="463ec-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="463ec-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="463ec-121">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="463ec-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="463ec-122">分析接口</span><span class="sxs-lookup"><span data-stu-id="463ec-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="463ec-123">分析</span><span class="sxs-lookup"><span data-stu-id="463ec-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
