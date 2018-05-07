---
title: ICorDebugEval::CreateValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d67784daee055106f104d74d098b9926c6de2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue 方法
其初始值为零或 null 创建指定类型的值。  
  
 此方法是.NET Framework 2.0 版中过时。 使用[icordebugeval2:: Createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `elementType`  
 [in]值为[CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md)指定值的类型的枚举。  
  
 `pElementClass`  
 [in]指向[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)指定的值的类，如果类型不是基元类型的对象。  
  
 `ppValue`  
 [out]一个表示值的"ICorDebugValue"对象的地址指针。  
  
## <a name="remarks"></a>备注  
 `CreateValue` 创建`ICorDebugValue`使用函数求值的唯一目的是给定类型的对象。 此值对象可以用于将用户常量作为参数传递。  
  
 如果值的类型为基元类型，其初始值为零或 null。 使用[icordebuggenericvalue:: Setvalue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)设置基元类型的值。  
  
 如果值`elementType`是 ELEMENT_TYPE_CLASS，获取"ICorDebugReferenceValue"(在返回`ppValue`) 表示空对象引用。 此对象可用于向函数求值的对象引用参数传递 null。 无法设置`ICorDebugValue`任何内容; 它始终仍是 null。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.1、 1.0  
  
## <a name="see-also"></a>请参阅  
    
 [CreateValueForType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 ICorDebugValue
