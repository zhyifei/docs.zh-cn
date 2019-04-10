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
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206585"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="3e276-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="3e276-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="3e276-103">[.NET Framework 4.7 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="3e276-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="3e276-104">通知探查器时完成的动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="3e276-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e276-105">语法</span><span class="sxs-lookup"><span data-stu-id="3e276-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e276-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e276-106">Parameters</span></span>  
<span data-ttu-id="3e276-107">[in]</span><span class="sxs-lookup"><span data-stu-id="3e276-107">[in]</span></span> `functionId`  
<span data-ttu-id="3e276-108">内存中函数的 JIT 编译开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="3e276-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="3e276-109">[in]</span><span class="sxs-lookup"><span data-stu-id="3e276-109">[in]</span></span> `hrStatus`   
<span data-ttu-id="3e276-110">一个值，指示 JIT 编译是否成功。</span><span class="sxs-lookup"><span data-stu-id="3e276-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="3e276-111">[in]</span><span class="sxs-lookup"><span data-stu-id="3e276-111">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="3e276-112">若要指示，阻止可能会导致运行时等待调用的线程返回从此回调;`false`以指示，阻止不会影响运行时的操作。</span><span class="sxs-lookup"><span data-stu-id="3e276-112">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="3e276-113">备注</span><span class="sxs-lookup"><span data-stu-id="3e276-113">Remarks</span></span>  

<span data-ttu-id="3e276-114">每当已完成的动态方法的 JIT 编译时，将触发此回调。</span><span class="sxs-lookup"><span data-stu-id="3e276-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="3e276-115">这包括各种 IL 存根 （stub） 和 LCG 方法。</span><span class="sxs-lookup"><span data-stu-id="3e276-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="3e276-116">其目标是向探查器编写器提供足够的信息来标识用户的已编译的方法。</span><span class="sxs-lookup"><span data-stu-id="3e276-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="3e276-117">值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。</span><span class="sxs-lookup"><span data-stu-id="3e276-117">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e276-118">要求</span><span class="sxs-lookup"><span data-stu-id="3e276-118">Requirements</span></span>  
 <span data-ttu-id="3e276-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e276-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e276-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e276-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e276-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e276-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3e276-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3e276-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e276-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e276-123">See also</span></span>

- [<span data-ttu-id="3e276-124">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="3e276-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="3e276-125">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="3e276-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
