---
title: ICorProfiler回调8：:DynamicMethodJIT编译启动方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177041"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="617cd-102">ICorProfiler回调8：:DynamicMethodJIT编译启动方法</span><span class="sxs-lookup"><span data-stu-id="617cd-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="617cd-103">[在 .NET 框架 4.7 和更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="617cd-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="617cd-104">每当开始动态方法的 JIT 编译时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="617cd-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="617cd-105">语法</span><span class="sxs-lookup"><span data-stu-id="617cd-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="617cd-106">parameters</span><span class="sxs-lookup"><span data-stu-id="617cd-106">Parameters</span></span>  
<span data-ttu-id="617cd-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="617cd-107">[in] `functionId`</span></span>  
<span data-ttu-id="617cd-108">启动 JIT 编译的内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="617cd-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="617cd-109">[在]`fIsSafeToBlock`指示阻塞可能导致运行时等待调用线程从此回调
`true`返回;`false`指示阻塞不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="617cd-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="617cd-110">[在]`pILHeader`指向方法 IL 标头的第一个字节的指针。</span><span class="sxs-lookup"><span data-stu-id="617cd-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="617cd-111">[在]`cbILHeader` IL 标头中的字节数。</span><span class="sxs-lookup"><span data-stu-id="617cd-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="617cd-112">备注</span><span class="sxs-lookup"><span data-stu-id="617cd-112">Remarks</span></span>  

<span data-ttu-id="617cd-113">每当编译动态方法时，就会触发此回调。</span><span class="sxs-lookup"><span data-stu-id="617cd-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="617cd-114">这包括各种 IL 存根和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="617cd-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="617cd-115">其目的是向探查器编写器提供足够的信息，以便向用户标识编译的方法。</span><span class="sxs-lookup"><span data-stu-id="617cd-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="617cd-116">`functionId`值不能用于解析到其元数据令牌，因为动态方法没有元数据。</span><span class="sxs-lookup"><span data-stu-id="617cd-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="617cd-117">指针`pILHeader`仅在回调期间有效。</span><span class="sxs-lookup"><span data-stu-id="617cd-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="617cd-118">要求</span><span class="sxs-lookup"><span data-stu-id="617cd-118">Requirements</span></span>  
 <span data-ttu-id="617cd-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="617cd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="617cd-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="617cd-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="617cd-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="617cd-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="617cd-122">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="617cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617cd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="617cd-123">See also</span></span>

- [<span data-ttu-id="617cd-124">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="617cd-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="617cd-125">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="617cd-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
