---
title: "ICorDebugFunction3::GetActiveReJitRequestILCode 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugFunction3.GetActiveReJitRequestILCode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6459297a2a04728ca87801bfc8484acec384a45c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="1a029-102">ICorDebugFunction3::GetActiveReJitRequestILCode 方法</span><span class="sxs-lookup"><span data-stu-id="1a029-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="1a029-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="1a029-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1a029-104">获取到的接口指针[ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)包含活动 ReJIT 请求中的 IL。</span><span class="sxs-lookup"><span data-stu-id="1a029-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a029-105">语法</span><span class="sxs-lookup"><span data-stu-id="1a029-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a029-106">参数</span><span class="sxs-lookup"><span data-stu-id="1a029-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="1a029-107">指向活动 ReJIT 请求中的 IL 的指针。</span><span class="sxs-lookup"><span data-stu-id="1a029-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a029-108">备注</span><span class="sxs-lookup"><span data-stu-id="1a029-108">Remarks</span></span>  
 <span data-ttu-id="1a029-109">如果此 `ICorDebugFunction3` 对象表示的方法具有活动 ReJIT 请求，则 `ppReJitedILCode` 将返回指向其 IL 的指针。</span><span class="sxs-lookup"><span data-stu-id="1a029-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="1a029-110">如果没有任何活动的请求，然后是常见的情况，`ppReJitedILCode`是**null**。</span><span class="sxs-lookup"><span data-stu-id="1a029-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="1a029-111">只需执行返回从之后，ReJIT 请求将变为活动状态[icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="1a029-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="1a029-112">可能尚未对它进行 JIT 编译，而且线程可能仍然在原始版本的代码中执行。</span><span class="sxs-lookup"><span data-stu-id="1a029-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="1a029-113">探查器的调用期间，ReJIT 请求变为非活动状态[icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1a029-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="1a029-114">即使还原了 IL 之后，线程仍然可在 JIT 编译 (ReJIT) 的代码中执行。</span><span class="sxs-lookup"><span data-stu-id="1a029-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a029-115">要求</span><span class="sxs-lookup"><span data-stu-id="1a029-115">Requirements</span></span>  
 <span data-ttu-id="1a029-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a029-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a029-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a029-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a029-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a029-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a029-119">**.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a029-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a029-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a029-120">See Also</span></span>  
 [<span data-ttu-id="1a029-121">ICorDebugFunction3 接口</span><span class="sxs-lookup"><span data-stu-id="1a029-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [<span data-ttu-id="1a029-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="1a029-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1a029-123">ReJIT: 操作方法指南</span><span class="sxs-lookup"><span data-stu-id="1a029-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
