---
title: COR_PRF_HIGH_MONITOR 枚举
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: fc0251624738a06d1be7081ebd099e97f7278a15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283145"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="7e015-102">COR_PRF_HIGH_MONITOR 枚举</span><span class="sxs-lookup"><span data-stu-id="7e015-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="7e015-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="7e015-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="7e015-104">除了在[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举中找到的标记外，还提供了标志，在加载时，探查器可以为[ICorProfilerInfo5：： SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法指定这些标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e015-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e015-105">Syntax</span></span>  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="7e015-106">Members</span><span class="sxs-lookup"><span data-stu-id="7e015-106">Members</span></span>  
  
|<span data-ttu-id="7e015-107">成员</span><span class="sxs-lookup"><span data-stu-id="7e015-107">Member</span></span>|<span data-ttu-id="7e015-108">说明</span><span class="sxs-lookup"><span data-stu-id="7e015-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="7e015-109">不设置任何标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="7e015-110">控制在 CLR 程序集引用闭包遍历期间添加程序集引用的[ICorProfilerCallback6：： GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="7e015-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="7e015-111">控制与内存中模块关联的符号流更新的[ICorProfilerCallback7：： ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="7e015-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="7e015-112">控制[ICorProfilerCallback9：:D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md)回调，用于指示动态方法何时被垃圾回收和卸载。</span><span class="sxs-lookup"><span data-stu-id="7e015-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="7e015-113">仅适用于 .NET Core 3.0 和更高版本：禁用探查器的[分层编译](../../../core/whats-new/dotnet-core-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="7e015-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="7e015-114">仅适用于 .NET Core 3.0 和更高版本：提供轻型 GC 分析选项与[`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)比较。</span><span class="sxs-lookup"><span data-stu-id="7e015-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="7e015-115">仅控制[GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)、 [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)和[GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="7e015-115">Controls only the  [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="7e015-116">与 `COR_PRF_MONITOR_GC` 标志不同，`COR_PRF_HIGH_BASIC_GC` 不会禁用并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7e015-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="7e015-117">仅适用于 .NET Core 3.0 和更高版本：仅为压缩 Gc 启用[MovedReferences](icorprofilercallback-movedreferences-method.md)和[MovedReferences2](icorprofilercallback4-movedreferences2-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="7e015-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="7e015-118">仅限 .NET Core 3.0 及更高版本：与[`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)类似，但仅提供有关大型对象堆（LOH）的对象分配的信息。</span><span class="sxs-lookup"><span data-stu-id="7e015-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="7e015-119">表示需要配置增强的映像的所有 `COR_PRF_HIGH_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="7e015-120">它对应于[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举中的 `COR_PRF_REQUIRE_PROFILE_IMAGE` 标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="7e015-121">表示可以在将探查器附加到运行中的应用之后进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="7e015-122">表示只能在初始化过程中进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="7e015-123">如果尝试从其他位置更改这些标志中的任何一个标志，则会产生一个指示失败的 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="7e015-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e015-124">备注</span><span class="sxs-lookup"><span data-stu-id="7e015-124">Remarks</span></span>

<span data-ttu-id="7e015-125">`COR_PRF_HIGH_MONITOR` 标志与[ICorProfilerInfo5：： GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)和[ICorProfilerInfo5：： SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法的 `pdwEventsHigh` 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="7e015-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="7e015-126">从 .NET Framework 4.6.1 开始，`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` 的值从0更改为 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` （0x00000002）。</span><span class="sxs-lookup"><span data-stu-id="7e015-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="7e015-127">从 .NET Framework 4.7.2 开始，其值从 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` 改为 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`。</span><span class="sxs-lookup"><span data-stu-id="7e015-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

<span data-ttu-id="7e015-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` 旨在成为一个位掩码，表示只能在初始化期间设置的所有标志。</span><span class="sxs-lookup"><span data-stu-id="7e015-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="7e015-129">尝试在其他任何位置更改这些标志会导致失败的 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="7e015-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e015-130">要求</span><span class="sxs-lookup"><span data-stu-id="7e015-130">Requirements</span></span>

<span data-ttu-id="7e015-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e015-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="7e015-132">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e015-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="7e015-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e015-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="7e015-134">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e015-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e015-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e015-135">See also</span></span>

- [<span data-ttu-id="7e015-136">分析枚举</span><span class="sxs-lookup"><span data-stu-id="7e015-136">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [<span data-ttu-id="7e015-137">COR_PRF_MONITOR 枚举</span><span class="sxs-lookup"><span data-stu-id="7e015-137">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="7e015-138">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="7e015-138">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
