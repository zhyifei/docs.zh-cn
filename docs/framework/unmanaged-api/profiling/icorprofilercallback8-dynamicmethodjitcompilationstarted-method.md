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
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454745"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="36232-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="36232-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="36232-103">[在.NET Framework 4.7 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="36232-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="36232-104">通知探查器时的动态方法的 JIT 编译已开始。</span><span class="sxs-lookup"><span data-stu-id="36232-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36232-105">语法</span><span class="sxs-lookup"><span data-stu-id="36232-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36232-106">参数</span><span class="sxs-lookup"><span data-stu-id="36232-106">Parameters</span></span>  
<span data-ttu-id="36232-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="36232-107">[in] `functionId`</span></span>  
<span data-ttu-id="36232-108">有关哪些 JIT 启动编译内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="36232-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="36232-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="36232-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="36232-110">`true` 若要指示阻止可能导致运行时等待从此回调; 中返回调用线程`false`以指示，阻止将不会影响运行时该操作。</span><span class="sxs-lookup"><span data-stu-id="36232-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="36232-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="36232-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="36232-112">指向方法的 IL 标头的第一个字节的指针。</span><span class="sxs-lookup"><span data-stu-id="36232-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="36232-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="36232-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="36232-114">IL 标头中的字节数。</span><span class="sxs-lookup"><span data-stu-id="36232-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="36232-115">备注</span><span class="sxs-lookup"><span data-stu-id="36232-115">Remarks</span></span>  

<span data-ttu-id="36232-116">每当一个动态方法进行 JIT 编译，时会触发此回调。</span><span class="sxs-lookup"><span data-stu-id="36232-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="36232-117">这包括各种 IL 存根 （stub） 和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="36232-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="36232-118">其目标是探查器编写器提供足够的信息来标识向用户的已编译的方法。</span><span class="sxs-lookup"><span data-stu-id="36232-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="36232-119">`functionId` 值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。</span><span class="sxs-lookup"><span data-stu-id="36232-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="36232-120">`pILHeader`指针在回调过程才有效。</span><span class="sxs-lookup"><span data-stu-id="36232-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="36232-121">要求</span><span class="sxs-lookup"><span data-stu-id="36232-121">Requirements</span></span>  
 <span data-ttu-id="36232-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36232-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36232-123">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36232-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36232-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36232-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36232-125">**.NET framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36232-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36232-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="36232-126">See Also</span></span>  
 [<span data-ttu-id="36232-127">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="36232-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [<span data-ttu-id="36232-128">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="36232-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
