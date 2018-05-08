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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8 接口
[在.NET Framework 4.7 和更高版本中受支持]  

 一个子类[ICorProfilerCallback7](icorprofilercallback7-interface.md)提供公共语言运行时用于通知探查器启动并完成动态方法的 JIT 编译的回叫方法。 
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|通知探查器已启动的动态方法的 JIT 编译。|  
|[DynamicMethodJITCompilationFinished 方法](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|通知探查器已完成的动态方法的 JIT 编译。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
**.NET framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅  
[分析接口](profiling-interfaces.md)   
[ICorProfilerCallback9 接口](icorprofilercallback9-interface.md)
