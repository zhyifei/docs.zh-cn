---
title: ICorProfilerCallback8：:D ynamicMethodJITCompilationFinished 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136575"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="f521b-102">ICorProfilerCallback8：:D ynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="f521b-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="f521b-103">[.NET Framework 4.7 及更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="f521b-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="f521b-104">当动态方法的 JIT 编译完成时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="f521b-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f521b-105">语法</span><span class="sxs-lookup"><span data-stu-id="f521b-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f521b-106">参数</span><span class="sxs-lookup"><span data-stu-id="f521b-106">Parameters</span></span>  
<span data-ttu-id="f521b-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="f521b-107">[in] `functionId`</span></span>  
<span data-ttu-id="f521b-108">开始 JIT 编译的内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="f521b-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="f521b-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="f521b-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="f521b-110">一个值，该值指示 JIT 编译是否成功。</span><span class="sxs-lookup"><span data-stu-id="f521b-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="f521b-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="f521b-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="f521b-112">`true` 指示阻止可能会导致运行时等待调用线程从此回调返回;`false`，指示阻止操作不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="f521b-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="f521b-113">备注</span><span class="sxs-lookup"><span data-stu-id="f521b-113">Remarks</span></span>  

<span data-ttu-id="f521b-114">只要动态方法的 JIT 编译完成，就会触发此回调。</span><span class="sxs-lookup"><span data-stu-id="f521b-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="f521b-115">这包括各种 IL 存根和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="f521b-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="f521b-116">其目标是为探查器编写者提供足够的信息，以便向用户标识编译的方法。</span><span class="sxs-lookup"><span data-stu-id="f521b-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="f521b-117">由于动态方法没有元数据，因此不能使用 `functionId` 值解析为其元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f521b-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="f521b-118">要求</span><span class="sxs-lookup"><span data-stu-id="f521b-118">Requirements</span></span>  
 <span data-ttu-id="f521b-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f521b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f521b-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f521b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f521b-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f521b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f521b-122">**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f521b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f521b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f521b-123">See also</span></span>

- [<span data-ttu-id="f521b-124">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="f521b-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="f521b-125">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="f521b-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
