---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12414064bf0651eab443951bde2a50dcff7b2291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992090"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="d5e3a-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated 方法</span><span class="sxs-lookup"><span data-stu-id="d5e3a-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="d5e3a-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="d5e3a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d5e3a-104">每次更新与内存中模块关联的符号流时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e3a-105">语法</span><span class="sxs-lookup"><span data-stu-id="d5e3a-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5e3a-106">参数</span><span class="sxs-lookup"><span data-stu-id="d5e3a-106">Parameters</span></span>  
 <span data-ttu-id="d5e3a-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="d5e3a-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="d5e3a-108">已更新的符号流的内存中模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5e3a-109">备注</span><span class="sxs-lookup"><span data-stu-id="d5e3a-109">Remarks</span></span>  
 <span data-ttu-id="d5e3a-110">通过设置控制此回调[COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)时调用事件掩码标志[ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5e3a-111">将引发此事件不当前符号隐式创建或修改通过<xref:System.Reflection.Emit>Api。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="d5e3a-112">甚至当符号中提供了预先对托管的重载之一<xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType>方法，包括`rawSymbolStore`参数来指定符号的程序集，运行时可能实际上将关联的符号数据与模块直到后[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调发生。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="d5e3a-113">此事件提供了一个更高版本的机会来收集此类模块的符号。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e3a-114">要求</span><span class="sxs-lookup"><span data-stu-id="d5e3a-114">Requirements</span></span>  
 <span data-ttu-id="d5e3a-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5e3a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e3a-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5e3a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5e3a-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5e3a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5e3a-118">**.NET Framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e3a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e3a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5e3a-119">See also</span></span>

- [<span data-ttu-id="d5e3a-120">ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="d5e3a-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="d5e3a-121">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="d5e3a-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="d5e3a-122">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="d5e3a-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
