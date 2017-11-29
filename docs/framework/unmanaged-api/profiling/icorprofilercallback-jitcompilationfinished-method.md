---
title: "ICorProfilerCallback::JITCompilationFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9719ce1474c2111692c6176655b75bd2d7edf923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="372f0-102">ICorProfilerCallback::JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="372f0-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="372f0-103">通知探查器在实时 (JIT) 编译器已完成编译函数。</span><span class="sxs-lookup"><span data-stu-id="372f0-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="372f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="372f0-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="372f0-105">参数</span><span class="sxs-lookup"><span data-stu-id="372f0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="372f0-106">[in]已编译的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="372f0-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="372f0-107">[in]指示是否编译成功的值。</span><span class="sxs-lookup"><span data-stu-id="372f0-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="372f0-108">[in]一个值，该值向探查器阻止是否会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="372f0-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="372f0-109">值是`true`如果阻止可能导致运行时，等待调用的线程，以返回从此回调; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="372f0-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="372f0-110">尽管值`true`不会造成损害运行时、 但可能会扭曲分析结果。</span><span class="sxs-lookup"><span data-stu-id="372f0-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="372f0-111">要求</span><span class="sxs-lookup"><span data-stu-id="372f0-111">Requirements</span></span>  
 <span data-ttu-id="372f0-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="372f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="372f0-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="372f0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="372f0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="372f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="372f0-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="372f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372f0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="372f0-116">See Also</span></span>  
 [<span data-ttu-id="372f0-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="372f0-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="372f0-118">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="372f0-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
