---
title: ICorDebugExceptionObjectCallStackEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975987"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>ICorDebugExceptionObjectCallStackEnum 接口
为嵌入在异常对象中的调用堆栈信息提供枚举器。 此接口是 ICorDebugEnum 接口的子类。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum：： Next](icordebugexceptionobjectcallstackenum-next-method.md)|获取指定数量的[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)对象，这些对象包含有关异常对象的调用堆栈的信息。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugExceptionObjectCallStackEnum`接口实现 ICorDebugEnum 接口。  
  
 `ICorDebugExceptionObjectCallStackEnum`实例通过调用[ICorDebugExceptionObjectValue：： EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)方法填充[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)对象。 可以通过调用[ICorDebugExceptionObjectCallStackEnum：： Next](icordebugexceptionobjectcallstackenum-next-method.md)方法枚举集合中的调用堆栈项  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
