---
title: COR_PRF_HIGH_MONITOR 枚举
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 5c6e34746368a7658c43fe0e2472000c29292569
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175208"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="55bf3-102">COR_PRF_HIGH_MONITOR 枚举</span><span class="sxs-lookup"><span data-stu-id="55bf3-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="55bf3-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="55bf3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="55bf3-104">除了[在COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)枚举中找到的标志外，探查器在加载时可以指定到[ICorProfilerInfo5：：setEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="55bf3-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55bf3-105">语法</span><span class="sxs-lookup"><span data-stu-id="55bf3-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="55bf3-106">成员</span><span class="sxs-lookup"><span data-stu-id="55bf3-106">Members</span></span>  
  
|<span data-ttu-id="55bf3-107">成员</span><span class="sxs-lookup"><span data-stu-id="55bf3-107">Member</span></span>|<span data-ttu-id="55bf3-108">说明</span><span class="sxs-lookup"><span data-stu-id="55bf3-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="55bf3-109">不设置任何标志。</span><span class="sxs-lookup"><span data-stu-id="55bf3-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="55bf3-110">控制[ICorProfiler 回调6：：获取组装参考](icorprofilercallback6-getassemblyreferences-method.md)回调，用于在 CLR 程序集引用闭合演练期间添加程序集引用。</span><span class="sxs-lookup"><span data-stu-id="55bf3-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="55bf3-111">控制[ICorProfiler 回调7：：模块内存符号更新](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)回调，以更新与内存中模块关联的符号流的更新。</span><span class="sxs-lookup"><span data-stu-id="55bf3-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="55bf3-112">控制[ICorProfiler Callback9：:DynamicMethod未加载](icorprofilercallback9-dynamicmethodunloaded-method.md)回调，用于指示动态方法何时被垃圾回收和卸载。</span><span class="sxs-lookup"><span data-stu-id="55bf3-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="55bf3-113">.NET Core 3.0 及更高版本：禁用探查器[的分层编译](../../../core/whats-new/dotnet-core-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="55bf3-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="55bf3-114">.NET Core 3.0 及更高版本：提供与[`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)的轻量级 GC 分析选项。</span><span class="sxs-lookup"><span data-stu-id="55bf3-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="55bf3-115">仅控制[垃圾回收启动](icorprofilercallback2-garbagecollectionstarted-method.md)、[垃圾回收完成](icorprofilercallback2-garbagecollectionfinished-method.md)和[获取生成绑定](icorprofilerinfo2-getgenerationbounds-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="55bf3-115">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="55bf3-116">与`COR_PRF_MONITOR_GC`标志不同，`COR_PRF_HIGH_BASIC_GC`不禁用并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="55bf3-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="55bf3-117">.NET Core 3.0 及更高版本：启用[移动引用](icorprofilercallback-movedreferences-method.md)和[移动引用2](icorprofilercallback4-movedreferences2-method.md)回调，仅用于压缩 G。</span><span class="sxs-lookup"><span data-stu-id="55bf3-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="55bf3-118">.NET Core 3.0 及更高版本：[`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)与 类似，但仅提供有关大型对象堆 （LOH） 对象分配的信息。</span><span class="sxs-lookup"><span data-stu-id="55bf3-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="55bf3-119">表示需要配置增强的映像的所有 `COR_PRF_HIGH_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="55bf3-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="55bf3-120">它对应于COR_PRF_MONITOR枚`COR_PRF_REQUIRE_PROFILE_IMAGE`举中的标志[COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="55bf3-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="55bf3-121">表示可以在将探查器附加到运行中的应用之后进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="55bf3-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="55bf3-122">表示只能在初始化过程中进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。</span><span class="sxs-lookup"><span data-stu-id="55bf3-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="55bf3-123">如果尝试从其他位置更改这些标志中的任何一个标志，则会产生一个指示失败的 `HRESULT` 值。</span><span class="sxs-lookup"><span data-stu-id="55bf3-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55bf3-124">备注</span><span class="sxs-lookup"><span data-stu-id="55bf3-124">Remarks</span></span>

<span data-ttu-id="55bf3-125">标志`COR_PRF_HIGH_MONITOR`与`pdwEventsHigh`[ICorProfilerInfo5：：getEventMask2](icorprofilerinfo5-geteventmask2-method.md)和[ICorProfilerInfo5：：setEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法的参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="55bf3-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="55bf3-126">从 .NET 框架 4.6.1 开始，将`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`的值从`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`0 更改为 （0x00000002）。</span><span class="sxs-lookup"><span data-stu-id="55bf3-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="55bf3-127">从 .NET 框架 4.7.2 开始，其`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`值`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`从 更改为 。</span><span class="sxs-lookup"><span data-stu-id="55bf3-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="55bf3-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE`旨在成为一个位掩码，表示仅在初始化期间才能设置的所有标志。</span><span class="sxs-lookup"><span data-stu-id="55bf3-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="55bf3-129">尝试在其他地方更改这些标志会导致失败`HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="55bf3-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="55bf3-130">要求</span><span class="sxs-lookup"><span data-stu-id="55bf3-130">Requirements</span></span>

<span data-ttu-id="55bf3-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55bf3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="55bf3-132">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55bf3-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="55bf3-133">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55bf3-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="55bf3-134">**.NET 框架版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55bf3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55bf3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55bf3-135">See also</span></span>

- [<span data-ttu-id="55bf3-136">分析枚举</span><span class="sxs-lookup"><span data-stu-id="55bf3-136">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="55bf3-137">COR_PRF_MONITOR 枚举</span><span class="sxs-lookup"><span data-stu-id="55bf3-137">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="55bf3-138">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="55bf3-138">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
