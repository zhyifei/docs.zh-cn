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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207590"
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
 中`mdFieldDef`引用描述字段的元数据的令牌。  
  
 `ppValue`  
 弄一个指向 "ICorDebugValue" 对象的指针，该对象表示指定字段的值。  
  
## <a name="remarks"></a>备注  
 参数中指定的类 `pClass` 必须位于对象值的类的层次结构中，并且字段必须是该类的字段。  
  
 `GetFieldValue`对于泛型对象和泛型类，该方法仍将成功。 例如，如果 MyDictionary \< V> 继承自字典 \< 字符串，V>，而对象值的类型为 MyDictionary \< int32>，则 `ICorDebugClass` 为字典 \< K，V> 传递对象将成功获取字典 \< 字符串 int32> 的字段。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
