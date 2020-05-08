---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: e45b180ac6d943d89740ad7ae10500ea4ad1aa9c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975961"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法
获取一个枚举器，该枚举器指向嵌入到异常对象中的调用堆栈。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>参数  
 ppCallStackEnum  
 弄指向[ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)接口对象地址的指针，该对象是托管异常对象的堆栈跟踪枚举器。  
  
## <a name="remarks"></a>备注  
 如果没有可用的调用堆栈信息，则该方法`S_OK`将返回，并且[ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)是长度为0的有效枚举器。 如果该方法无法检索堆栈跟踪信息，则返回值为`E_FAIL` ，并且不返回任何枚举器。  
  
 [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)对象负责从 exception 对象的`_stackTrace`字段解码堆栈跟踪数据。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugExceptionObjectValue 接口](icordebugexceptionobjectvalue-interface.md)
- [调试接口](debugging-interfaces.md)
