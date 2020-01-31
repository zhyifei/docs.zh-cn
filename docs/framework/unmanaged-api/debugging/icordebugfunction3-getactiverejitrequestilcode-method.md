---
title: ICorDebugFunction3::GetActiveReJitRequestILCode 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777729"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="11597-102">ICorDebugFunction3::GetActiveReJitRequestILCode 方法</span><span class="sxs-lookup"><span data-stu-id="11597-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="11597-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="11597-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="11597-104">获取一个接口指针，该指针指向包含活动 ReJIT 请求中的 IL 的[ICorDebugILCode](icordebugilcode-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="11597-104">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11597-105">语法</span><span class="sxs-lookup"><span data-stu-id="11597-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11597-106">参数</span><span class="sxs-lookup"><span data-stu-id="11597-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="11597-107">指向活动 ReJIT 请求中的 IL 的指针。</span><span class="sxs-lookup"><span data-stu-id="11597-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11597-108">备注</span><span class="sxs-lookup"><span data-stu-id="11597-108">Remarks</span></span>  
 <span data-ttu-id="11597-109">如果此 `ICorDebugFunction3` 对象表示的方法具有活动 ReJIT 请求，则 `ppReJitedILCode` 将返回指向其 IL 的指针。</span><span class="sxs-lookup"><span data-stu-id="11597-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="11597-110">如果没有活动请求（这是常见情况），则 `ppReJitedILCode` 为**null**。</span><span class="sxs-lookup"><span data-stu-id="11597-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="11597-111">ReJIT 请求在执行从[ICorProfilerCallback4：： GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)方法调用返回后变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="11597-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="11597-112">可能尚未对它进行 JIT 编译，而且线程可能仍然在原始版本的代码中执行。</span><span class="sxs-lookup"><span data-stu-id="11597-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="11597-113">在探查器调用[ICorProfilerInfo4：： RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)方法的过程中，ReJIT 请求将变为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="11597-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="11597-114">即使还原了 IL 之后，线程仍然可在 JIT 编译 (ReJIT) 的代码中执行。</span><span class="sxs-lookup"><span data-stu-id="11597-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11597-115">需求</span><span class="sxs-lookup"><span data-stu-id="11597-115">Requirements</span></span>  
 <span data-ttu-id="11597-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11597-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11597-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11597-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11597-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11597-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11597-119">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11597-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11597-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11597-120">See also</span></span>

- [<span data-ttu-id="11597-121">ICorDebugFunction3 接口</span><span class="sxs-lookup"><span data-stu-id="11597-121">ICorDebugFunction3 Interface</span></span>](icordebugfunction3-interface.md)
- [<span data-ttu-id="11597-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="11597-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="11597-123">ReJIT：操作方法指南</span><span class="sxs-lookup"><span data-stu-id="11597-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
