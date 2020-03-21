---
title: ICorProfiler回调8：:DynamicMethodJIT编译完成方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175104"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="2eacd-102">ICorProfiler回调8：:DynamicMethodJIT编译完成方法</span><span class="sxs-lookup"><span data-stu-id="2eacd-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="2eacd-103">[在 .NET 框架 4.7 和更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="2eacd-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="2eacd-104">每当动态方法的 JIT 编译完成时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="2eacd-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eacd-105">语法</span><span class="sxs-lookup"><span data-stu-id="2eacd-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2eacd-106">parameters</span><span class="sxs-lookup"><span data-stu-id="2eacd-106">Parameters</span></span>  
<span data-ttu-id="2eacd-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="2eacd-107">[in] `functionId`</span></span>  
<span data-ttu-id="2eacd-108">启动 JIT 编译的内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="2eacd-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="2eacd-109">[在]`hrStatus`指示 JIT 编译是否成功的值。</span><span class="sxs-lookup"><span data-stu-id="2eacd-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="2eacd-110">[在]`fIsSafeToBlock`指示阻塞可能导致运行时等待调用线程从此回调
`true`返回;`false`指示阻塞不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="2eacd-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="2eacd-111">备注</span><span class="sxs-lookup"><span data-stu-id="2eacd-111">Remarks</span></span>  

<span data-ttu-id="2eacd-112">每当动态方法的 JIT 编译完成时，都会触发此回调。</span><span class="sxs-lookup"><span data-stu-id="2eacd-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="2eacd-113">这包括各种 IL 存根和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="2eacd-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="2eacd-114">其目的是向探查器编写器提供足够的信息，以便向用户标识编译的方法。</span><span class="sxs-lookup"><span data-stu-id="2eacd-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="2eacd-115">`functionId`值不能用于解析到其元数据令牌，因为动态方法没有元数据。</span><span class="sxs-lookup"><span data-stu-id="2eacd-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="2eacd-116">要求</span><span class="sxs-lookup"><span data-stu-id="2eacd-116">Requirements</span></span>  
 <span data-ttu-id="2eacd-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2eacd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eacd-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2eacd-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2eacd-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2eacd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2eacd-120">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2eacd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eacd-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eacd-121">See also</span></span>

- [<span data-ttu-id="2eacd-122">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="2eacd-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="2eacd-123">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="2eacd-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
