---
title: ICorProfilerCallback8 接口
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4516c8f9673052b521c1f0f594978236fef1e0ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136453"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8 接口
[.NET Framework 4.7 及更高版本中支持]  

 提供回调方法的[ICorProfilerCallback7](icorprofilercallback7-interface.md)的子类，公共语言运行时使用该方法通知探查器动态方法的 JIT 编译已开始和完成。 
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|通知探查器已经开始对动态方法进行 JIT 编译。|  
|[DynamicMethodJITCompilationFinished 方法](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|通知探查器已完成动态方法的 JIT 编译。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [Profiling 接口](profiling-interfaces.md)
- [ICorProfilerCallback9 接口](icorprofilercallback9-interface.md)
