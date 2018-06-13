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
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452372"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="ee930-102">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="ee930-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="ee930-103">[.NET Framework 4.7.2 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="ee930-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="ee930-104">一个子类[ICorProfilerCallback8](icorprofilercallback8-interface.md)提供公共语言运行时用于通知探查器动态方法已被垃圾回收并随后卸载的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ee930-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee930-105">方法</span><span class="sxs-lookup"><span data-stu-id="ee930-105">Methods</span></span>  
  
|<span data-ttu-id="ee930-106">方法</span><span class="sxs-lookup"><span data-stu-id="ee930-106">Method</span></span>|<span data-ttu-id="ee930-107">描述</span><span class="sxs-lookup"><span data-stu-id="ee930-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee930-108">DynamicMethodUnloaded 方法</span><span class="sxs-lookup"><span data-stu-id="ee930-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="ee930-109">通知探查器动态方法已被垃圾回收并随后卸载。</span><span class="sxs-lookup"><span data-stu-id="ee930-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee930-110">要求</span><span class="sxs-lookup"><span data-stu-id="ee930-110">Requirements</span></span>  
 <span data-ttu-id="ee930-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee930-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee930-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee930-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="ee930-113">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ee930-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ee930-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee930-114">See Also</span></span>  
<span data-ttu-id="ee930-115">[分析接口](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="ee930-115">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
<span data-ttu-id="ee930-116">[ICorProfilerCallback8 接口](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="ee930-116">[ICorProfilerCallback8 Interface](icorprofilercallback9-interface.md) </span></span>  
<span data-ttu-id="ee930-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span><span class="sxs-lookup"><span data-stu-id="ee930-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted method](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span></span>  
[<span data-ttu-id="ee930-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ee930-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
