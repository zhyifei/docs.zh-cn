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
ms.openlocfilehash: 49b5ead8b5428d855b7dab81dced1de6325fd07b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationFinished 方法
[在.NET Framework 4.7 和更高版本中受支持]  
  
通知探查器，只要已完成的动态方法的 JIT 编译。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
#### <a name="parameters"></a>参数  
[in] `functionId`  
有关哪些 JIT 启动编译内存中函数的标识符。   

[in] `hrStatus`   
一个值，该值指示是否已成功 JIT 编译。

[in] `fIsSafeToBlock`   
`true` 若要指示阻止可能导致运行时等待从此回调; 中返回调用线程`false`以指示，阻止将不会影响运行时该操作。  

## <a name="remarks"></a>备注  

每当完成动态方法的 JIT 编译，时会触发此回调。 这包括各种 IL 存根 （stub） 和 LCG 方法。 其目标是探查器编写器提供足够的信息来标识向用户的已编译的方法。

> [!NOTE]
> `functionId` 值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>请参阅  
 [DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
 [ICorProfilerCallback8 接口](icorprofilercallback8-interface.md)
