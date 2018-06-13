---
title: ICorProfilerCallback8 接口
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455278"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="62419-102">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="62419-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="62419-103">[在.NET Framework 4.7 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="62419-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="62419-104">一个子类[ICorProfilerCallback7](icorprofilercallback7-interface.md)提供公共语言运行时用于通知探查器启动并完成动态方法的 JIT 编译的回叫方法。</span><span class="sxs-lookup"><span data-stu-id="62419-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="62419-105">方法</span><span class="sxs-lookup"><span data-stu-id="62419-105">Methods</span></span>  
  
|<span data-ttu-id="62419-106">方法</span><span class="sxs-lookup"><span data-stu-id="62419-106">Method</span></span>|<span data-ttu-id="62419-107">描述</span><span class="sxs-lookup"><span data-stu-id="62419-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62419-108">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="62419-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="62419-109">通知探查器已启动的动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="62419-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="62419-110">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="62419-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="62419-111">通知探查器已完成的动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="62419-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62419-112">要求</span><span class="sxs-lookup"><span data-stu-id="62419-112">Requirements</span></span>  
 <span data-ttu-id="62419-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62419-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62419-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62419-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="62419-115">**.NET framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="62419-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="62419-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="62419-116">See Also</span></span>  
<span data-ttu-id="62419-117">[分析接口](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="62419-117">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
[<span data-ttu-id="62419-118">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="62419-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
