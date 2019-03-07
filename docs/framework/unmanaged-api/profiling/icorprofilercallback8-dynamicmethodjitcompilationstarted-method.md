---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 170d0b20069724a4e1845be0250b2897daa10dee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501235"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="bc80b-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="bc80b-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="bc80b-103">[.NET Framework 4.7 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="bc80b-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="bc80b-104">通知探查器时的动态方法的 JIT 编译已启动。</span><span class="sxs-lookup"><span data-stu-id="bc80b-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc80b-105">语法</span><span class="sxs-lookup"><span data-stu-id="bc80b-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc80b-106">参数</span><span class="sxs-lookup"><span data-stu-id="bc80b-106">Parameters</span></span>  
<span data-ttu-id="bc80b-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="bc80b-107">[in] `functionId`</span></span>  
<span data-ttu-id="bc80b-108">内存中函数的 JIT 编译开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="bc80b-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="bc80b-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="bc80b-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="bc80b-110">`true` 若要指示，阻止可能会导致运行时等待调用的线程返回从此回调;`false`以指示，阻止不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="bc80b-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="bc80b-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="bc80b-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="bc80b-112">指向方法的 IL 标头的第一个字节的指针。</span><span class="sxs-lookup"><span data-stu-id="bc80b-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="bc80b-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="bc80b-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="bc80b-114">IL 标头中的字节数。</span><span class="sxs-lookup"><span data-stu-id="bc80b-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="bc80b-115">备注</span><span class="sxs-lookup"><span data-stu-id="bc80b-115">Remarks</span></span>  

<span data-ttu-id="bc80b-116">JIT 编译动态方法时，将触发此回调。</span><span class="sxs-lookup"><span data-stu-id="bc80b-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="bc80b-117">这包括各种 IL 存根 （stub） 和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="bc80b-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="bc80b-118">其目标是向探查器编写器提供足够的信息来标识用户的已编译的方法。</span><span class="sxs-lookup"><span data-stu-id="bc80b-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="bc80b-119">`functionId` 值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。</span><span class="sxs-lookup"><span data-stu-id="bc80b-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="bc80b-120">`pILHeader`指针回调期间才有效。</span><span class="sxs-lookup"><span data-stu-id="bc80b-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc80b-121">要求</span><span class="sxs-lookup"><span data-stu-id="bc80b-121">Requirements</span></span>  
 <span data-ttu-id="bc80b-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc80b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc80b-123">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc80b-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc80b-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc80b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc80b-125">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bc80b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc80b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc80b-126">See also</span></span>
- [<span data-ttu-id="bc80b-127">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="bc80b-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="bc80b-128">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="bc80b-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
