---
title: ICorProfilerCallback::JITFunctionPitched 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91bc626e2c75cd7eb2eafad0fc26d343e5b278e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530719"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="813ba-102">ICorProfilerCallback::JITFunctionPitched 方法</span><span class="sxs-lookup"><span data-stu-id="813ba-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="813ba-103">通知探查器的已实时 (JIT) 的函数的编译已从内存中删除。</span><span class="sxs-lookup"><span data-stu-id="813ba-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="813ba-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="813ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="813ba-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="813ba-106">[in]已删除的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="813ba-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="813ba-107">备注</span><span class="sxs-lookup"><span data-stu-id="813ba-107">Remarks</span></span>  
 <span data-ttu-id="813ba-108">如果调用已删除的函数时，探查器会收到新的 JIT 编译事件时重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="813ba-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="813ba-109">目前，公共语言运行时 (CLR) JIT 编译器不会删除函数从内存，所以此回调当前未使用且不会收到探查器。</span><span class="sxs-lookup"><span data-stu-id="813ba-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="813ba-110">值`functionId`直到重新编译该函数不有效。</span><span class="sxs-lookup"><span data-stu-id="813ba-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="813ba-111">该函数重新编译时，相同`functionId`将使用的值。</span><span class="sxs-lookup"><span data-stu-id="813ba-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="813ba-112">要求</span><span class="sxs-lookup"><span data-stu-id="813ba-112">Requirements</span></span>  
 <span data-ttu-id="813ba-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="813ba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="813ba-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="813ba-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="813ba-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="813ba-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="813ba-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="813ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813ba-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="813ba-117">See also</span></span>
- [<span data-ttu-id="813ba-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="813ba-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
