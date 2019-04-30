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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991999"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="d8263-102">ICorProfilerCallback9::DynamicMethodUnloaded 方法</span><span class="sxs-lookup"><span data-stu-id="d8263-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="d8263-103">[.NET Framework 4.7.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="d8263-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="d8263-104">垃圾回收并随后卸载的动态方法时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="d8263-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8263-105">语法</span><span class="sxs-lookup"><span data-stu-id="d8263-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8263-106">参数</span><span class="sxs-lookup"><span data-stu-id="d8263-106">Parameters</span></span>  
<span data-ttu-id="d8263-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="d8263-107">[in] `functionId`</span></span>  
<span data-ttu-id="d8263-108">已被垃圾收集和卸载的内存中函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="d8263-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="d8263-109">要求</span><span class="sxs-lookup"><span data-stu-id="d8263-109">Requirements</span></span>  
 <span data-ttu-id="d8263-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8263-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8263-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8263-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8263-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8263-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8263-113">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8263-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8263-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8263-114">See also</span></span>

- [<span data-ttu-id="d8263-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="d8263-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="d8263-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="d8263-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="d8263-117">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="d8263-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="d8263-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="d8263-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
