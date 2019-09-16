---
title: ICorDebugEval 接口
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd29067f819ba69305f7ae8620729cd443915a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931949"
---
# <a name="icordebugeval-interface"></a>ICorDebugEval 接口

提供使调试器能够在正在调试的代码的上下文中执行代码的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Abort 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|中止此`ICorDebugEval`对象当前正在执行的计算。|  
|[CallFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|设置对指定函数的调用。 （在 .NET Framework 版本2.0 中已过时; 请改用[ICorDebugEval2：： CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) 。）|  
|[CreateValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|获取一个接口指针，该指针指向指定类型的 "ICorDebugValue" 对象，其初始值为零或 null。 （在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) 。）|  
|[GetResult 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|获取一个`ICorDebugValue`接口指针，该指针指向包含计算结果的。|  
|[GetThread 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|获取一个接口指针，该指针指向正在执行或将执行此计算的 "ICorDebugThread"。|  
|[IsActive 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|获取一个值，该值指示此`ICorDebugEval`对象当前是否正在执行。|  
|[NewArray 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|分配指定元素类型和维度的新数组。 （在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) 。）|  
|[NewObject 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|分配一个新的对象实例，并调用指定的构造函数方法。 （在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) 。）|  
|[NewObjectNoConstructor 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|分配指定类型的新对象实例，而不尝试调用构造函数方法。 （在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) 。）|  
|[NewString 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|使用指定的内容分配新的字符串对象。|  
  
## <a name="remarks"></a>备注  
 在用于执行计算的特定线程的上下文中创建对象。`ICorDebugEval` 给定计算中使用的所有对象和类型必须位于同一个应用程序域中。 该应用程序域不需要与该线程的当前应用程序域相同。 评估可以嵌套。  
  
 直到调试程序调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)并收到[ICorDebugManagedCallback：： EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)回调后，计算的操作才会完成。 如果需要在不允许其他线程运行的情况下使用评估功能，请在调用 [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 之前使用 [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) 或 [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md) 挂起线程。  
  
 由于正在进行计算时用户代码正在运行，因此可能会发生任何调试事件，包括类加载和断点。 对于这些事件，调试器将接收回拨。 评估的状态将被视为正常程序状态的一部分。 堆栈链将是一个`CHAIN_FUNC_EVAL`链（请参阅 "CorDebugStepReason" 枚举和[ICorDebugChain：： GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)方法）。 完整的调试器 API 将继续正常运行。  
  
 如果发生死锁或无限循环，用户代码可能永远无法完成。 在这种情况下，必须在恢复程序之前调用[ICorDebugEval：： Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) 。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
