---
title: ICorProfiler回拨9：:Dynamic方法未加载方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177028"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="68c9a-102">ICorProfiler回拨9：:Dynamic方法未加载方法</span><span class="sxs-lookup"><span data-stu-id="68c9a-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="68c9a-103">[在 .NET 框架 4.7.2 和更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="68c9a-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="68c9a-104">每当收集动态方法并随后卸载时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="68c9a-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c9a-105">语法</span><span class="sxs-lookup"><span data-stu-id="68c9a-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68c9a-106">parameters</span><span class="sxs-lookup"><span data-stu-id="68c9a-106">Parameters</span></span>  
<span data-ttu-id="68c9a-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="68c9a-107">[in] `functionId`</span></span>  
<span data-ttu-id="68c9a-108">已垃圾回收和卸载的内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="68c9a-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="68c9a-109">要求</span><span class="sxs-lookup"><span data-stu-id="68c9a-109">Requirements</span></span>  
 <span data-ttu-id="68c9a-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68c9a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68c9a-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68c9a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="68c9a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68c9a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68c9a-113">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="68c9a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c9a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68c9a-114">See also</span></span>

- [<span data-ttu-id="68c9a-115">ICorProfiler回调8.动态方法JIT编译启动方法</span><span class="sxs-lookup"><span data-stu-id="68c9a-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="68c9a-116">ICorProfiler回调8.动态方法JIT编译完成方法</span><span class="sxs-lookup"><span data-stu-id="68c9a-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="68c9a-117">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="68c9a-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="68c9a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="68c9a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
