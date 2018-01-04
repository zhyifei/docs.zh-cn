---
title: "ICorProfilerCallback::JITFunctionPitched 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48432911d7844e6519689961c985da37219179a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="5f26d-102">ICorProfilerCallback::JITFunctionPitched 方法</span><span class="sxs-lookup"><span data-stu-id="5f26d-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="5f26d-103">通知探查器的已实时 (JIT) 的函数的编译已从内存中删除。</span><span class="sxs-lookup"><span data-stu-id="5f26d-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f26d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f26d-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f26d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f26d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5f26d-106">[in]已删除的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="5f26d-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f26d-107">备注</span><span class="sxs-lookup"><span data-stu-id="5f26d-107">Remarks</span></span>  
 <span data-ttu-id="5f26d-108">如果调用已删除的函数时，探查器将收到新的 JIT 编译事件重新编译函数时。</span><span class="sxs-lookup"><span data-stu-id="5f26d-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="5f26d-109">目前，公共语言运行时 (CLR) JIT 编译器不会删除函数从内存，所以此回调当前未使用且未将收到由探查器。</span><span class="sxs-lookup"><span data-stu-id="5f26d-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="5f26d-110">值`functionId`才会有效重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="5f26d-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="5f26d-111">当重新编译函数时，相同`functionId`将使用的值。</span><span class="sxs-lookup"><span data-stu-id="5f26d-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f26d-112">惠?</span><span class="sxs-lookup"><span data-stu-id="5f26d-112">Requirements</span></span>  
 <span data-ttu-id="5f26d-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f26d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f26d-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f26d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f26d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f26d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f26d-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f26d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f26d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f26d-117">See Also</span></span>  
 [<span data-ttu-id="5f26d-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="5f26d-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
