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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175091"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="682a1-102">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="682a1-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="682a1-103">[在 .NET 框架 4.7 和更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="682a1-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="682a1-104">[ICorProfilerCallback7](icorprofilercallback7-interface.md)的子类，它提供通用语言运行时使用的回调方法，以通知探查器动态方法的 JIT 编译已启动并完成。</span><span class="sxs-lookup"><span data-stu-id="682a1-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="682a1-105">方法</span><span class="sxs-lookup"><span data-stu-id="682a1-105">Methods</span></span>  
  
|<span data-ttu-id="682a1-106">方法</span><span class="sxs-lookup"><span data-stu-id="682a1-106">Method</span></span>|<span data-ttu-id="682a1-107">说明</span><span class="sxs-lookup"><span data-stu-id="682a1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="682a1-108">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="682a1-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="682a1-109">通知探查器动态方法的 JIT 编译已启动。</span><span class="sxs-lookup"><span data-stu-id="682a1-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="682a1-110">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="682a1-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="682a1-111">通知探查器动态方法的 JIT 编译已完成。</span><span class="sxs-lookup"><span data-stu-id="682a1-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="682a1-112">要求</span><span class="sxs-lookup"><span data-stu-id="682a1-112">Requirements</span></span>  
 <span data-ttu-id="682a1-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="682a1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="682a1-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="682a1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="682a1-115">**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="682a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="682a1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="682a1-116">See also</span></span>

- [<span data-ttu-id="682a1-117">分析接口</span><span class="sxs-lookup"><span data-stu-id="682a1-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="682a1-118">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="682a1-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
