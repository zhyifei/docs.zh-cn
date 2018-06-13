---
title: ICorProfilerCallback9::DynamicMethodUnloaded 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452398"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="27d81-102">ICorProfilerCallback9::DynamicMethodUnloaded 方法</span><span class="sxs-lookup"><span data-stu-id="27d81-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="27d81-103">[.NET Framework 4.7.2 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="27d81-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="27d81-104">垃圾回收并随后卸载的动态方法时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="27d81-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d81-105">语法</span><span class="sxs-lookup"><span data-stu-id="27d81-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27d81-106">参数</span><span class="sxs-lookup"><span data-stu-id="27d81-106">Parameters</span></span>  
<span data-ttu-id="27d81-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="27d81-107">[in] `functionId`</span></span>  
<span data-ttu-id="27d81-108">已被垃圾回收并卸载内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="27d81-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="27d81-109">要求</span><span class="sxs-lookup"><span data-stu-id="27d81-109">Requirements</span></span>  
 <span data-ttu-id="27d81-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27d81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27d81-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27d81-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27d81-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27d81-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27d81-113">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27d81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d81-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="27d81-114">See Also</span></span>  
[<span data-ttu-id="27d81-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="27d81-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="27d81-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="27d81-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="27d81-117">[ICorProfilerCallback9 接口](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="27d81-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="27d81-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="27d81-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
