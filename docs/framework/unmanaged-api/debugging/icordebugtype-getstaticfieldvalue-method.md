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
ms.openlocfilehash: 95183701987d3ddec3835a17c5d256c25c2c4c64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132070"
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
 仅当类型为 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 时，才可以使用 `GetStaticFieldValue` 方法，如[ICorDebugType：： GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)方法所示。  
  
 对于非泛型类型，`GetStaticFieldValue` 执行的操作与对[ICorDebugType：： GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)返回的 ICorDebugClass 对象调用[ICorDebugClass：： GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)完全相同。  
  
 对于泛型类型，静态字段值将与特定实例化相关。 此外，如果静态字段可能是相对于线程、上下文或应用程序域的，则堆栈帧将有助于调试器确定正确的值。  
  
## <a name="remarks"></a>备注  
 仅当对 `ICorDebugType::GetType` 的调用返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 的值时，才能使用 `GetStaticFieldValue`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
