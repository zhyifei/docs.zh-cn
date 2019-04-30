---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049708"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationFinished 方法
[.NET Framework 4.7 和更高版本中受支持]  
  
通知探查器时完成的动态方法的 JIT 编译。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a>参数  
[in] `functionId`  
内存中函数的 JIT 编译开始的标识符。   

[in] `hrStatus`   
一个值，指示 JIT 编译是否成功。

[in] `fIsSafeToBlock`   
`true` 若要指示，阻止可能会导致运行时等待调用的线程返回从此回调;`false`以指示，阻止不会影响运行时的操作。  

## <a name="remarks"></a>备注  

每当已完成的动态方法的 JIT 编译时，将触发此回调。 这包括各种 IL 存根 （stub） 和 LCG 方法。 其目标是向探查器编写器提供足够的信息来标识用户的已编译的方法。

> [!NOTE]
> `functionId` 值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>请参阅

- [DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8 接口](icorprofilercallback8-interface.md)
