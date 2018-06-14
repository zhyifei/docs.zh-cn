---
title: COR_PRF_HIGH_MONITOR 枚举
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c92ba2b5eac5eb1368a7d7ccf3b666886f4ca92a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454709"
---
# <a name="corprfhighmonitor-enumeration"></a>COR_PRF_HIGH_MONITOR 枚举
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 提供除在中找到的标志[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)探查器可以指定到的枚举[icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法加载时。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,     
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,    
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|不设置任何标志。|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|控件[ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) CLR 程序集引用闭包审核期间添加程序集引用的回调。|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|控件[ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)回调的更新与内存中模块关联的符号流。|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|控件[ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md)回调，该值指示当一个动态方法已被垃圾收集和卸载。 <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|   
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|表示需要配置增强的映像的所有 `COR_PRF_HIGH_MONITOR` 标志。 它对应于`COR_PRF_REQUIRE_PROFILE_IMAGE`中标记出来[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|表示可以在将探查器附加到运行中的应用之后进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|表示只能在初始化过程中进行设置的所有 `COR_PRF_HIGH_MONITOR` 标志。 如果尝试从其他位置更改这些标志中的任何一个标志，则会产生一个指示失败的 `HRESULT` 值。|  
  
## <a name="remarks"></a>备注  
 `COR_PRF_HIGH_MONITOR`标志用于`pdwEventsHigh`参数[icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)和[icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。  
  
从开始[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)]的值`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`更改从 0 到`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`(0x00000002)。 从.NET Framework 4.7.2 开始，从更改其值`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`到`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`。   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` 被用于表示仅在初始化过程设置的所有标志的位掩码。 尝试更改任何其他位置将导致故障这些标志`HRESULT`。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [COR_PRF_MONITOR 枚举](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 [ICorProfilerInfo5 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
