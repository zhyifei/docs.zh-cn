---
title: ICorProfiler回调8：:DynamicMethodJIT编译完成方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175104"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfiler回调8：:DynamicMethodJIT编译完成方法
[在 .NET 框架 4.7 和更高版本中支持]  
  
每当动态方法的 JIT 编译完成时，通知探查器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a>parameters  
[in] `functionId`  
启动 JIT 编译的内存中函数的标识符。

[在]`hrStatus`指示 JIT 编译是否成功的值。

[在]`fIsSafeToBlock`指示阻塞可能导致运行时等待调用线程从此回调
`true`返回;`false`指示阻塞不会影响运行时的操作。  

## <a name="remarks"></a>备注  

每当动态方法的 JIT 编译完成时，都会触发此回调。 这包括各种 IL 存根和 LCG 方法。 其目的是向探查器编写器提供足够的信息，以便向用户标识编译的方法。

> [!NOTE]
> `functionId`值不能用于解析到其元数据令牌，因为动态方法没有元数据。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [DynamicMethodJITCompilationStarted 方法](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8 接口](icorprofilercallback8-interface.md)
