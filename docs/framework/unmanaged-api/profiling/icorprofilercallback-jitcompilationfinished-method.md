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
ms.openlocfilehash: 1bbdfa93913b9fdf8aa164c8ca6c35cd33a228df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449915"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="85d4d-102">ICorProfilerCallback::JITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="85d4d-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="85d4d-103">通知探查器，实时（JIT）编译器已完成编译函数。</span><span class="sxs-lookup"><span data-stu-id="85d4d-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="85d4d-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85d4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="85d4d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="85d4d-106">中已编译的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="85d4d-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="85d4d-107">中指示编译是否成功的值。</span><span class="sxs-lookup"><span data-stu-id="85d4d-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="85d4d-108">中指示探查器是否会影响运行时的操作的值。</span><span class="sxs-lookup"><span data-stu-id="85d4d-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="85d4d-109">如果阻止可能导致运行时等待调用线程从此回调返回，则值为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="85d4d-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="85d4d-110">尽管 `true` 的值不会损坏运行时，但它可能会使分析结果变形。</span><span class="sxs-lookup"><span data-stu-id="85d4d-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85d4d-111">要求</span><span class="sxs-lookup"><span data-stu-id="85d4d-111">Requirements</span></span>  
 <span data-ttu-id="85d4d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85d4d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d4d-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85d4d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85d4d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85d4d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85d4d-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d4d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85d4d-116">See also</span></span>

- [<span data-ttu-id="85d4d-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="85d4d-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="85d4d-118">JITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="85d4d-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
