---
title: ICorProfilerCallback4::ReJITCompilationFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ec2981cbee4675f9cd2a4fd13d507f50ad2a3ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597136"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="57af0-102">ICorProfilerCallback4::ReJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="57af0-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="57af0-103">通知探查器在实时 (JIT) 编译器已完成重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="57af0-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57af0-104">语法</span><span class="sxs-lookup"><span data-stu-id="57af0-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57af0-105">参数</span><span class="sxs-lookup"><span data-stu-id="57af0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="57af0-106">[in]已重新编译函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="57af0-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="57af0-107">[in] JIT 重新编译的函数的标识。</span><span class="sxs-lookup"><span data-stu-id="57af0-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="57af0-108">[in]一个值，指示 JIT 重新编译是否成功。</span><span class="sxs-lookup"><span data-stu-id="57af0-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="57af0-109">[in]`true`以指示，阻止可能会导致运行时等待调用的线程返回从此回调;`false`以指示，阻止不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="57af0-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="57af0-110">值为`true`不会损害了运行时，但可能会影响分析结果。</span><span class="sxs-lookup"><span data-stu-id="57af0-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57af0-111">要求</span><span class="sxs-lookup"><span data-stu-id="57af0-111">Requirements</span></span>  
 <span data-ttu-id="57af0-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57af0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57af0-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57af0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57af0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57af0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57af0-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57af0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57af0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="57af0-116">See also</span></span>

- [<span data-ttu-id="57af0-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="57af0-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="57af0-118">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="57af0-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="57af0-119">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="57af0-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="57af0-120">ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="57af0-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
