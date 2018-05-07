---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationStarted 方法
[在.NET Framework 4.7 和更高版本中受支持]  
  
通知探查器时的动态方法的 JIT 编译已开始。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a>参数  
[in] `functionId`  
有关哪些 JIT 启动编译内存中函数的标识符。   

[in] `fIsSafeToBlock`   
`true` 若要指示阻止可能导致运行时等待从此回调; 中返回调用线程`false`以指示，阻止将不会影响运行时该操作。  

[in] `pILHeader`    
指向方法的 IL 标头的第一个字节的指针。   

[in] `cbILHeader`    
IL 标头中的字节数。 

## <a name="remarks"></a>备注  

每当一个动态方法进行 JIT 编译，时会触发此回调。 这包括各种 IL 存根 （stub） 和 LCG 方法。 其目标是探查器编写器提供足够的信息来标识向用户的已编译的方法。

> [!NOTE]
> `functionId` 值不能用来解析为其元数据标记，因为动态方法不具有任何元数据。

`pILHeader`指针在回调过程才有效。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>请参阅  
 [DynamicMethodJITCompilationFinished 方法](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [ICorProfilerCallback8 接口](icorprofilercallback8-interface.md)
