---
title: ICorProfilerCallback9 接口
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136567"
---
# <a name="icorprofilercallback9-interface"></a>ICorProfilerCallback9 接口
[.NET Framework 4.7.2 和更高版本中支持]  

 提供回调方法的[ICorProfilerCallback8](icorprofilercallback8-interface.md)的子类，公共语言运行时使用该方法通知探查器动态方法已被垃圾回收并随后卸载。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DynamicMethodUnloaded 方法](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|通知探查器已对动态方法进行了垃圾回收并随后将其卸载。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>请参阅

- [Profiling 接口](profiling-interfaces.md)
- [ICorProfilerCallback8 接口](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationFinished 方法](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
