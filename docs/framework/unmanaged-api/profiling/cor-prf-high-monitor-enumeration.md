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
# <a name="cor_prf_high_monitor-enumeration"></a>COR_PRF_HIGH_MONITOR 枚举

[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
除了[在COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)枚举中找到的标志外，探查器在加载时可以指定到[ICorProfilerInfo5：：setEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|不设置任何标志。|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|控制[ICorProfiler 回调6：：获取组装参考](icorprofilercallback6-getassemblyreferences-method.md)回调，用于在 CLR 程序集引用闭合演练期间添加程序集引用。|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|控制[ICorProfiler 回调7：：模块内存符号更新](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)回调，以更新与内存中模块关联的符号流的更新。|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|控制[ICorProfiler Callback9：:DynamicMethod未加载](icorprofilercallback9-dynamicmethodunloaded-method.md)回调，用于指示动态方法何时被垃圾回收和卸载。 <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|.NET Core 3.0 及更高版本：禁用探查器[的分层编译](../../../core/whats-new/dotnet-core-3-0.md)。|
|`COR_PRF_HIGH_BASIC_GC`|.NET Core 3.0 及更高版本：提供与[`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)的轻量级 GC 分析选项。 仅控制[垃圾回收启动](icorprofilercallback2-garbagecollectionstarted-method.md)、[垃圾回收完成](icorprofilercallback2-garbagecollectionfinished-method.md)和[获取生成绑定](icorprofilerinfo2-getgenerationbounds-method.md)回调。 与`COR_PRF_MONITOR_GC`标志不同，`COR_PRF_HIGH_BASIC_GC`不禁用并发垃圾回收。|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|.NET Core 3.0 及更高版本：启用[移动引用](icorprofilercallback-movedreferences-method.md)和[移动引用2](icorprofilercallback4-movedreferences2-method.md)回调，仅用于压缩 G。|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET Core 3.0 及更高版本：[`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)与 类似，但仅提供有关大型对象堆 （LOH） 对象分配的信息。|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|表示需要配置增强的映像的所有 `COR_PRF_HIGH_MONITOR` 标志。 它对应于COR_PRF_MONITOR枚`COR_PRF_REQUIRE_PROFILE_IMAGE`举中的标志[COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)。|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|表示可以在将探查器附加到运行中的应用之后进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|表示只能在初始化过程中进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。 如果尝试从其他位置更改这些标志中的任何一个标志，则会产生一个指示失败的 `HRESULT` 值。|  
  
## <a name="remarks"></a>备注

标志`COR_PRF_HIGH_MONITOR`与`pdwEventsHigh`[ICorProfilerInfo5：：getEventMask2](icorprofilerinfo5-geteventmask2-method.md)和[ICorProfilerInfo5：：setEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法的参数一起使用。  
  
从 .NET 框架 4.6.1 开始，将`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`的值从`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`0 更改为 （0x00000002）。 从 .NET 框架 4.7.2 开始，其`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`值`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`从 更改为 。

`COR_PRF_HIGH_MONITOR_IMMUTABLE`旨在成为一个位掩码，表示仅在初始化期间才能设置的所有标志。 尝试在其他地方更改这些标志会导致失败`HRESULT`。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
**头文件：** CorProf.idl、CorProf.h  
  
**库：** CorGuids.lib  
  
**.NET 框架版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [分析枚举](profiling-enumerations.md)
- [COR_PRF_MONITOR 枚举](cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5 接口](icorprofilerinfo5-interface.md)
