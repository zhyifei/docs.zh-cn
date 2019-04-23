---
title: ICorProfilerCallback9 接口
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227751"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="e648e-102">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="e648e-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="e648e-103">[.NET Framework 4.7.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="e648e-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="e648e-104">子类[ICorProfilerCallback8](icorprofilercallback8-interface.md)提供公共语言运行时用于通知探查器动态方法已被垃圾回收并随后卸载的回调方法。</span><span class="sxs-lookup"><span data-stu-id="e648e-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e648e-105">方法</span><span class="sxs-lookup"><span data-stu-id="e648e-105">Methods</span></span>  
  
|<span data-ttu-id="e648e-106">方法</span><span class="sxs-lookup"><span data-stu-id="e648e-106">Method</span></span>|<span data-ttu-id="e648e-107">描述</span><span class="sxs-lookup"><span data-stu-id="e648e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e648e-108">DynamicMethodUnloaded 方法</span><span class="sxs-lookup"><span data-stu-id="e648e-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="e648e-109">通知探查器动态方法已被垃圾回收并随后卸载。</span><span class="sxs-lookup"><span data-stu-id="e648e-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e648e-110">要求</span><span class="sxs-lookup"><span data-stu-id="e648e-110">Requirements</span></span>  
 <span data-ttu-id="e648e-111">**平台：** 请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e648e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e648e-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e648e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="e648e-113">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e648e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e648e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e648e-114">See also</span></span>

- [<span data-ttu-id="e648e-115">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="e648e-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e648e-116">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="e648e-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="e648e-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="e648e-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="e648e-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="e648e-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
