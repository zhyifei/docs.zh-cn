---
title: ICorDebugExceptionDebugEvent::GetStackPointer 方法
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 4f84183dfc23ebc0d0fee9feeb21329c217b9cca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976013"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>ICorDebugExceptionDebugEvent::GetStackPointer 方法
获取此异常调试事件的堆栈指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a>参数  
 `pStackPointer`  
 [out] 指向此异常调试事件的堆栈指针的地址的指针。 有关详细信息，请参阅“备注”部分。  
  
## <a name="remarks"></a>备注  
 此堆栈指针的含义取决于事件类型，如下表所示。  
  
|事件类型|`pStackPointer` 值的含义|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|引发异常的帧的堆栈指针。|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|与引发的异常点最接近的用户代码帧的堆栈指针。|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|包含 catch 处理程序的帧的堆栈指针。|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pStackPointer` 为 **null**。|  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
 可以从[ICorDebugDebugEvent：： GetEventKind](icordebugdebugevent-geteventkind-method.md)方法获取事件类型。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [“ICor调试异常调试事件”接口](icordebugexceptiondebugevent-interface.md)
- [调试接口](debugging-interfaces.md)
