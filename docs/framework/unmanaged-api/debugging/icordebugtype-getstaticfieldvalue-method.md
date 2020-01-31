---
title: ICorDebugType::GetStaticFieldValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791272"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue 方法
获取一个指向 ICorDebugValue 对象的接口指针，该对象包含指定的堆栈帧中指定字段标记所引用的静态字段的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `fieldDef`  
 中指定静态字段的 `mdFieldDef` 标记。  
  
 `pFrame`  
 中指向表示堆栈帧的 ICorDebugFrame 的指针。  
  
 `ppValue`  
 弄一个指针，指向包含静态字段值的 `ICorDebugValue` 的地址。  
  
## <a name="remarks"></a>备注  
 仅当类型 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 时，才能使用 `GetStaticFieldValue` 方法，如[ICorDebugType：： GetType](icordebugtype-gettype-method.md)方法所示。  
  
 对于非泛型类型，`GetStaticFieldValue` 执行的操作与对[ICorDebugType：： GetClass](icordebugtype-getclass-method.md)返回的 ICorDebugClass 对象调用[ICorDebugClass：： GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)完全相同。  
  
 对于泛型类型，静态字段值将与特定实例化相关。 此外，如果静态字段可能是相对于线程、上下文或应用程序域的，则堆栈帧将有助于调试器确定正确的值。  
  
## <a name="remarks"></a>备注  
 仅当对 `ICorDebugType::GetType` 的调用返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 值时，才能使用 `GetStaticFieldValue`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
