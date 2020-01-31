---
title: ICorProfilerCallback7：： ModuleInMemorySymbolsUpdated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: 6fbb86fc63a26599ae83c81817dbcb9abfb88cc8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864683"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="ee13a-102">ICorProfilerCallback7：： ModuleInMemorySymbolsUpdated 方法</span><span class="sxs-lookup"><span data-stu-id="ee13a-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="ee13a-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="ee13a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="ee13a-104">只要更新与内存中模块关联的符号流，就会通知探查器。</span><span class="sxs-lookup"><span data-stu-id="ee13a-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee13a-105">语法</span><span class="sxs-lookup"><span data-stu-id="ee13a-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee13a-106">参数</span><span class="sxs-lookup"><span data-stu-id="ee13a-106">Parameters</span></span>  
 <span data-ttu-id="ee13a-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="ee13a-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="ee13a-108">已更新其符号流的内存中模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="ee13a-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee13a-109">备注</span><span class="sxs-lookup"><span data-stu-id="ee13a-109">Remarks</span></span>  
 <span data-ttu-id="ee13a-110">调用[ICorProfilerCallback5：： SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法时，可通过设置[COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md)事件掩码标志来控制此回调。</span><span class="sxs-lookup"><span data-stu-id="ee13a-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee13a-111">当前不会对通过 <xref:System.Reflection.Emit> Api 隐式创建或修改的符号引发此事件。</span><span class="sxs-lookup"><span data-stu-id="ee13a-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="ee13a-112">即使在对托管 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 方法的重载之一的调用中预先提供了符号（包括 `rawSymbolStore` 参数以指定程序集的符号），运行时也可能不会实际将符号数据与模块相关联，直到[ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调发生之后。</span><span class="sxs-lookup"><span data-stu-id="ee13a-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="ee13a-113">此事件提供稍后的机会来收集此类模块的符号。</span><span class="sxs-lookup"><span data-stu-id="ee13a-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee13a-114">需求</span><span class="sxs-lookup"><span data-stu-id="ee13a-114">Requirements</span></span>  
 <span data-ttu-id="ee13a-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee13a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee13a-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee13a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee13a-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee13a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee13a-118">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee13a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee13a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee13a-119">See also</span></span>

- [<span data-ttu-id="ee13a-120">ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="ee13a-120">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="ee13a-121">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="ee13a-121">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="ee13a-122">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="ee13a-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)
