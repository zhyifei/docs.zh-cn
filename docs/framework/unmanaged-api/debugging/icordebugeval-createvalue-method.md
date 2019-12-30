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
ms.openlocfilehash: 4bb04ba090be9cab551bc39d8d9f1be974c747d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085138"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue 方法
创建指定类型的值，其初始值为零或 null。  
  
 此方法在 .NET Framework 版本2.0 中已过时。 改[为使用 ICorDebugEval2：： CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) 。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `elementType`  
 中[CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md)枚举的一个值，该值指定值的类型。  
  
 `pElementClass`  
 中指向[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)对象的指针，该对象指定值的类（如果该类型不是基元类型）。  
  
 `ppValue`  
 弄指向表示值的 "ICorDebugValue" 对象地址的指针。  
  
## <a name="remarks"></a>备注  
 `CreateValue` 创建给定类型的 `ICorDebugValue` 对象，目的是在函数求值中使用它。 此值对象可用于将用户常数作为参数传递。  
  
 如果值的类型为基元类型，则其初始值为零或 null。 使用[ICorDebugGenericValue：： SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)设置基元类型的值。  
  
 如果 `elementType` 的值为 ELEMENT_TYPE_CLASS，则会收到表示 null 对象引用的 "ICorDebugReferenceValue" （在 `ppValue`中返回）。 您可以使用此对象将 null 传递给具有对象引用参数的函数求值。 不能将 `ICorDebugValue` 设置为任何内容;它始终为 null。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** 1.1、1.0  
  
## <a name="see-also"></a>请参阅

- [CreateValueForType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval 接口](icordebugeval-interface.md)
