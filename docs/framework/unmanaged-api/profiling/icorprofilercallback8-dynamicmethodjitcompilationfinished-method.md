---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b5ead8b5428d855b7dab81dced1de6325fd07b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="7a806-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="7a806-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="7a806-103">[在.NET Framework 4.7 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="7a806-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="7a806-104">通知探查器，只要已完成的动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="7a806-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a806-105">语法</span><span class="sxs-lookup"><span data-stu-id="7a806-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a806-106">参数</span><span class="sxs-lookup"><span data-stu-id="7a806-106">Parameters</span></span>  
<span data-ttu-id="7a806-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="7a806-107">[in] `functionId`</span></span>  
<span data-ttu-id="7a806-108">有关哪些 JIT 启动编译内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="7a806-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="7a806-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="7a806-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="7a806-110">一个值，该值指示是否已成功 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="7a806-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="7a806-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="7a806-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="7a806-112">`true` 若要指示阻止可能导致运行时等待从此回调; 中返回调用线程`false`以指示，阻止将不会影响运行时该操作。</span><span class="sxs-lookup"><span data-stu-id="7a806-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="7a806-113">备注</span><span class="sxs-lookup"><span data-stu-id="7a806-113">Remarks</span></span>  

<span data-ttu-id="7a806-114">每当完成动态方法的 JIT 编译，时会触发此回调。</span><span class="sxs-lookup"><span data-stu-id="7a806-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="7a806-115">这包括各种 IL 存根 （stub） 和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="7a806-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="7a806-116">其目标是探查器编写器提供足够的信息来标识向用户的已编译的方法。</span><span class="sxs-lookup"><span data-stu-id="7a806-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="7a806-117">`functionId` 值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。</span><span class="sxs-lookup"><span data-stu-id="7a806-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a806-118">要求</span><span class="sxs-lookup"><span data-stu-id="7a806-118">Requirements</span></span>  
 <span data-ttu-id="7a806-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a806-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a806-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a806-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a806-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a806-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a806-122">**.NET framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a806-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a806-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a806-123">See Also</span></span>  
 [<span data-ttu-id="7a806-124">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="7a806-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
 [<span data-ttu-id="7a806-125">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="7a806-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
