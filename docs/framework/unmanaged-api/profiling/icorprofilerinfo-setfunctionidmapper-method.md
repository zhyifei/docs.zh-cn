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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5aee9454024401513d381c50faf815b37371fbfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514369"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="10835-102">ICorProfilerInfo::SetFunctionIDMapper 方法</span><span class="sxs-lookup"><span data-stu-id="10835-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="10835-103">指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。</span><span class="sxs-lookup"><span data-stu-id="10835-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10835-104">语法</span><span class="sxs-lookup"><span data-stu-id="10835-104">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10835-105">参数</span><span class="sxs-lookup"><span data-stu-id="10835-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="10835-106">[in]一个指向[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)实现，它将调用映射`FunctionID`为其替代值的值。</span><span class="sxs-lookup"><span data-stu-id="10835-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10835-107">备注</span><span class="sxs-lookup"><span data-stu-id="10835-107">Remarks</span></span>  
 <span data-ttu-id="10835-108">备选方法`FunctionID`值将传递给探查器的输入/退出挂钩函数 ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)，并[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md))由指定的[ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="10835-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="10835-109">`FunctionIDMapper`可以设置在仅一次，并且建议将其设置[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="10835-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10835-110">要求</span><span class="sxs-lookup"><span data-stu-id="10835-110">Requirements</span></span>  
 <span data-ttu-id="10835-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10835-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10835-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10835-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10835-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10835-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10835-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10835-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10835-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="10835-115">See also</span></span>
- [<span data-ttu-id="10835-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="10835-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
