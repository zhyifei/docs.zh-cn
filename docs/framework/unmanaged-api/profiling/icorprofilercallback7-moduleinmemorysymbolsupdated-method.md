---
title: "ICorProfilerCallback7::ModuleInMemorySymbolsUpdated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 088749195165039639f58f4eb6444fb640ab4cec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="a0a39-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated 方法</span><span class="sxs-lookup"><span data-stu-id="a0a39-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="a0a39-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="a0a39-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="a0a39-104">每次更新与内存中模块关联的符号流时，通知探查器。</span><span class="sxs-lookup"><span data-stu-id="a0a39-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a39-105">语法</span><span class="sxs-lookup"><span data-stu-id="a0a39-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0a39-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0a39-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a0a39-107">已更新其符号流的内存中模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="a0a39-107">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0a39-108">备注</span><span class="sxs-lookup"><span data-stu-id="a0a39-108">Remarks</span></span>  
 <span data-ttu-id="a0a39-109">通过设置控制此回调[COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)事件掩码标志时调用[ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a0a39-109">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0a39-110">将引发此事件不当前符号隐式创建或修改通过<xref:System.Reflection.Emit>Api。</span><span class="sxs-lookup"><span data-stu-id="a0a39-110">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="a0a39-111">甚至当符号中提供了预先的托管的重载之一调用<xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType>方法包括`rawSymbolStore`自变量指定程序集，运行时的符号可能不实际的符号的数据将与模块关联直到后[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调发生。</span><span class="sxs-lookup"><span data-stu-id="a0a39-111">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="a0a39-112">此事件提供了更高版本机会收集此类模块的符号。</span><span class="sxs-lookup"><span data-stu-id="a0a39-112">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a39-113">要求</span><span class="sxs-lookup"><span data-stu-id="a0a39-113">Requirements</span></span>  
 <span data-ttu-id="a0a39-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0a39-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a39-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0a39-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0a39-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0a39-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0a39-117">**.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a39-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a39-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0a39-118">See Also</span></span>  
 [<span data-ttu-id="a0a39-119">ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="a0a39-119">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="a0a39-120">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="a0a39-120">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="a0a39-121">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="a0a39-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
