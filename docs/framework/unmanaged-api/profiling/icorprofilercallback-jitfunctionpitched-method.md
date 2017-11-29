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
ms.openlocfilehash: a5b14bc5735c83897e818ca2038455e0c6510e27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="f19c0-102">ICorProfilerCallback::JITFunctionPitched 方法</span><span class="sxs-lookup"><span data-stu-id="f19c0-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="f19c0-103">通知探查器的已实时 (JIT) 的函数的编译已从内存中删除。</span><span class="sxs-lookup"><span data-stu-id="f19c0-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="f19c0-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f19c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="f19c0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f19c0-106">[in]已删除的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="f19c0-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f19c0-107">备注</span><span class="sxs-lookup"><span data-stu-id="f19c0-107">Remarks</span></span>  
 <span data-ttu-id="f19c0-108">如果调用已删除的函数时，探查器将收到新的 JIT 编译事件重新编译函数时。</span><span class="sxs-lookup"><span data-stu-id="f19c0-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="f19c0-109">目前，公共语言运行时 (CLR) JIT 编译器不会删除函数从内存，所以此回调当前未使用且未将收到由探查器。</span><span class="sxs-lookup"><span data-stu-id="f19c0-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="f19c0-110">值`functionId`才会有效重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="f19c0-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="f19c0-111">当重新编译函数时，相同`functionId`将使用的值。</span><span class="sxs-lookup"><span data-stu-id="f19c0-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19c0-112">要求</span><span class="sxs-lookup"><span data-stu-id="f19c0-112">Requirements</span></span>  
 <span data-ttu-id="f19c0-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f19c0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f19c0-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f19c0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f19c0-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f19c0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f19c0-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f19c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19c0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f19c0-117">See Also</span></span>  
 [<span data-ttu-id="f19c0-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f19c0-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
