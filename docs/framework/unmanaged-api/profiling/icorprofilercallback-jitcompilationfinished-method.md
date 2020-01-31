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
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866242"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="08308-102">ICorProfilerCallback::JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="08308-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="08308-103">通知探查器，实时（JIT）编译器已完成编译函数。</span><span class="sxs-lookup"><span data-stu-id="08308-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08308-104">语法</span><span class="sxs-lookup"><span data-stu-id="08308-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08308-105">参数</span><span class="sxs-lookup"><span data-stu-id="08308-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="08308-106">\[中] 编译的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="08308-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="08308-107">\[中的] 一个值，该值指示编译是否成功。</span><span class="sxs-lookup"><span data-stu-id="08308-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="08308-108">\[中的] 一个值，该值指示探查器是否会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="08308-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="08308-109">如果阻止可能导致运行时等待调用线程从此回调返回，则值为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="08308-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="08308-110">尽管 `true` 的值不会损坏运行时，但它可能会使分析结果变形。</span><span class="sxs-lookup"><span data-stu-id="08308-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="08308-111">需求</span><span class="sxs-lookup"><span data-stu-id="08308-111">Requirements</span></span>  
 <span data-ttu-id="08308-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08308-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08308-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08308-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08308-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08308-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08308-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08308-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08308-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08308-116">See also</span></span>

- [<span data-ttu-id="08308-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="08308-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="08308-118">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="08308-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
