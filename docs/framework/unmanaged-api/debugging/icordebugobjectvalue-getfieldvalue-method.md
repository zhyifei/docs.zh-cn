---
title: ICorDebugObjectValue::GetFieldValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095883"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue 方法
获取此对象值的指定类的指定字段的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `pClass`  
 中一个指向 "ICorDebugClass" 对象的指针，该对象表示要获取其字段值的类。  
  
 `fieldDef`  
 中一个 `mdFieldDef` 标记，它引用描述字段的元数据。  
  
 `ppValue`  
 弄一个指向 "ICorDebugValue" 对象的指针，该对象表示指定字段的值。  
  
## <a name="remarks"></a>备注  
 在 `pClass` 参数中指定的类必须位于对象值的类的层次结构中，并且字段必须是该类的字段。  
  
 对于泛型对象和泛型类，`GetFieldValue` 方法仍将成功。 例如，如果 MyDictionary\<V > 从字典继承\<string，V >，并且对象值的类型为 MyDictionary\<int32 >，则为字典传递 `ICorDebugClass` 对象\<K，V > 将成功获取的字段字典\<字符串，int32 >。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
