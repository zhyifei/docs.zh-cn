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
ms.openlocfilehash: 96cdfb79c1573648173305d6ee789aa8db030ff8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211005"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="3db4c-102">ICorProfilerCallback9::DynamicMethodUnloaded 方法</span><span class="sxs-lookup"><span data-stu-id="3db4c-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="3db4c-103">[.NET Framework 4.7.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="3db4c-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="3db4c-104">垃圾回收并随后卸载的动态方法时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="3db4c-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db4c-105">语法</span><span class="sxs-lookup"><span data-stu-id="3db4c-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3db4c-106">参数</span><span class="sxs-lookup"><span data-stu-id="3db4c-106">Parameters</span></span>  
<span data-ttu-id="3db4c-107">[in]</span><span class="sxs-lookup"><span data-stu-id="3db4c-107">[in]</span></span> `functionId`  
<span data-ttu-id="3db4c-108">已被垃圾收集和卸载的内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="3db4c-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="3db4c-109">要求</span><span class="sxs-lookup"><span data-stu-id="3db4c-109">Requirements</span></span>  
 <span data-ttu-id="3db4c-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3db4c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db4c-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3db4c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3db4c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3db4c-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3db4c-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3db4c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3db4c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3db4c-114">See also</span></span>

- [<span data-ttu-id="3db4c-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="3db4c-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="3db4c-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="3db4c-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="3db4c-117">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="3db4c-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="3db4c-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="3db4c-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
