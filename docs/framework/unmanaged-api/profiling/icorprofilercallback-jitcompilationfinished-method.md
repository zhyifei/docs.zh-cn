---
title: ICorProfilerCallback::JITCompilationFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d2e75d357b1f56df676163744015a1a3f77c17b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530744"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="4671a-102">ICorProfilerCallback::JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="4671a-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="4671a-103">通知探查器在实时 (JIT) 编译器已完成编译函数。</span><span class="sxs-lookup"><span data-stu-id="4671a-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4671a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4671a-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4671a-105">参数</span><span class="sxs-lookup"><span data-stu-id="4671a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4671a-106">[in]已编译的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="4671a-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4671a-107">[in]指示编译是否成功的值。</span><span class="sxs-lookup"><span data-stu-id="4671a-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="4671a-108">[in]一个值，该值向探查器是否阻止会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="4671a-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="4671a-109">值是`true`如果阻塞可能会导致运行时等待调用的线程返回从此回调; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="4671a-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="4671a-110">尽管值`true`不会造成损害运行时、 但可能会扭曲分析结果。</span><span class="sxs-lookup"><span data-stu-id="4671a-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4671a-111">要求</span><span class="sxs-lookup"><span data-stu-id="4671a-111">Requirements</span></span>  
 <span data-ttu-id="4671a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4671a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4671a-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4671a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4671a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4671a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4671a-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4671a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4671a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4671a-116">See also</span></span>
- [<span data-ttu-id="4671a-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4671a-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4671a-118">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="4671a-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
