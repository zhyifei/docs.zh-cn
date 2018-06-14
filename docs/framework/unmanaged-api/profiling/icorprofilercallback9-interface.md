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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452372"
---
# <a name="icorprofilercallback9-interface"></a>ICorProfilerCallback9 接口
[.NET Framework 4.7.2 和更高版本中受支持]  

 一个子类[ICorProfilerCallback8](icorprofilercallback8-interface.md)提供公共语言运行时用于通知探查器动态方法已被垃圾回收并随后卸载的回调方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DynamicMethodUnloaded 方法](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|通知探查器动态方法已被垃圾回收并随后卸载。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>请参阅  
[分析接口](profiling-interfaces.md)   
[ICorProfilerCallback8 接口](icorprofilercallback9-interface.md)   
[ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)   
[ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
