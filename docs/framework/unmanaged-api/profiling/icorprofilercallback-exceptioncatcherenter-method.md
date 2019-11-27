---
title: ICorProfilerCallback::ExceptionCatcherEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9c9cd0b042dc22f35c38e349ab8881dafc602731
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445014"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter 方法
通知探查器控制正在传递到适当的 `catch` 块。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 中包含 `catch` 块的函数的标识符。  
  
 `objectId`  
 中正在处理的异常的标识符。  
  
## <a name="remarks"></a>备注  
 仅当 catch 点位于用实时（JIT）编译器编译的代码中时，才会调用 `ExceptionCatcherEnter` 方法。 在非托管代码中或在运行时的内部代码中捕获的异常将不会调用此通知。 该 `objectId` 值将再次传递，因为垃圾回收可能会因为 `ExceptionThrown` 通知而移动了对象。  
  
 探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。 如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。  
  
 探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ExceptionCatcherLeave 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
