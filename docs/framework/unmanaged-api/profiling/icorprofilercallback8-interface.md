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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175091"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8 接口
[在 .NET 框架 4.7 和更高版本中支持]  

 [ICorProfilerCallback7](icorprofilercallback7-interface.md)的子类，它提供通用语言运行时使用的回调方法，以通知探查器动态方法的 JIT 编译已启动并完成。
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|通知探查器动态方法的 JIT 编译已启动。|  
|[DynamicMethodJITCompilationFinished 方法](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|通知探查器动态方法的 JIT 编译已完成。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [分析接口](profiling-interfaces.md)
- [ICorProfilerCallback9 接口](icorprofilercallback9-interface.md)
