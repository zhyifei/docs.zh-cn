---
title: ICorDebugValue::GetType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 7def2bd2c0f3ab501fdb918a0e9a7ee154159b78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791159"
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType 方法
获取此 "ICorDebugValue" 对象的基元类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>参数  
 `pType`  
 弄一个指针，指向 "CorElementType" 枚举的值，该值指示值的类型。  
  
## <a name="remarks"></a>备注  
 如果对象是复杂的运行时类型，则可以通过 `ICorDebugValue` 接口的相应子类检查该类型。 例如，从 `ICorDebugValue`继承的 "ICorDebugObjectValue" 表示复杂类型。  
  
 `GetType` 和[ICorDebugObjectValue：： GetClass](icordebugobjectvalue-getclass-method.md)方法都返回有关值类型的信息。 它们都是由识别泛型的[ICorDebugValue2：： GetExactType](icordebugvalue2-getexacttype-method.md)方法取代的。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅
