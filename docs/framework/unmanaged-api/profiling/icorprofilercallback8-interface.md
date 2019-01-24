---
title: ICorProfilerCallback8 Interface
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
ms.openlocfilehash: a3bdf79582619777a22c80caac5b4e90d603f3a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675010"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="ca109-102">ICorProfilerCallback8 Interface</span><span class="sxs-lookup"><span data-stu-id="ca109-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="ca109-103">[.NET Framework 4.7 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="ca109-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="ca109-104">子类[ICorProfilerCallback7](icorprofilercallback7-interface.md)提供公共语言运行时用于通知探查器中的动态方法的 JIT 编译已启动和完成的回调方法。</span><span class="sxs-lookup"><span data-stu-id="ca109-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="ca109-105">方法</span><span class="sxs-lookup"><span data-stu-id="ca109-105">Methods</span></span>  
  
|<span data-ttu-id="ca109-106">方法</span><span class="sxs-lookup"><span data-stu-id="ca109-106">Method</span></span>|<span data-ttu-id="ca109-107">描述</span><span class="sxs-lookup"><span data-stu-id="ca109-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca109-108">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="ca109-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="ca109-109">通知探查器已启动的动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="ca109-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="ca109-110">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ca109-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="ca109-111">通知探查器已完成的动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="ca109-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca109-112">要求</span><span class="sxs-lookup"><span data-stu-id="ca109-112">Requirements</span></span>  
 <span data-ttu-id="ca109-113">**平台：** 请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca109-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca109-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca109-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="ca109-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ca109-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ca109-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca109-116">See also</span></span>
- [<span data-ttu-id="ca109-117">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="ca109-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ca109-118">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="ca109-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
