---
title: ICorProfilerInfo::SetFunctionIDMapper 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 52ab9a089b5def4f3db2f99abc5a718d66cca739
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863447"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="ec329-102">ICorProfilerInfo::SetFunctionIDMapper 方法</span><span class="sxs-lookup"><span data-stu-id="ec329-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="ec329-103">指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。</span><span class="sxs-lookup"><span data-stu-id="ec329-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec329-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec329-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec329-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec329-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="ec329-106">中指向[FunctionIDMapper](functionidmapper-function.md)实现的指针，将调用该指针以将 `FunctionID` 值映射到其可选值。</span><span class="sxs-lookup"><span data-stu-id="ec329-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec329-107">备注</span><span class="sxs-lookup"><span data-stu-id="ec329-107">Remarks</span></span>  
 <span data-ttu-id="ec329-108">`FunctionID` 值的替代项将传递到由[ICorProfilerInfo2：： SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)方法指定的探查器的函数入口/出口挂钩（[FunctionEnter2](functionenter2-function.md)、 [FunctionLeave2](functionleave2-function.md)和[FunctionTailcall2](functiontailcall2-function.md)）。</span><span class="sxs-lookup"><span data-stu-id="ec329-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="ec329-109">`FunctionIDMapper` 只能设置一次，建议你在[ICorProfilerCallback：： Initialize](icorprofilercallback-initialize-method.md)回调中进行设置。</span><span class="sxs-lookup"><span data-stu-id="ec329-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec329-110">需求</span><span class="sxs-lookup"><span data-stu-id="ec329-110">Requirements</span></span>  
 <span data-ttu-id="ec329-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec329-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec329-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec329-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec329-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec329-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec329-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec329-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec329-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec329-115">See also</span></span>

- [<span data-ttu-id="ec329-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ec329-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
