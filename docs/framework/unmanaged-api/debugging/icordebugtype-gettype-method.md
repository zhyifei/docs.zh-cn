---
title: ICorDebugType::GetType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 7f3010cccc584288608b3f6ba95efbeb95f271fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132060"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType 方法
获取一个 CorElementType 值，该值描述此 ICorDebugType 表示的公共语言运行时（CLR） <xref:System.Type> 的本机类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>参数  
 `ty`  
 弄一个指针，指向 `CorElementType` 枚举的值，该值指示此 `ICorDebugType` 表示的 CLR <xref:System.Type>。  
  
## <a name="remarks"></a>备注  
 如果 `ty` 的值为 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE，则可以调用[ICorDebugType：： GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)方法来获取泛型类型的实例化类型;否则，请不要调用 `ICorDebugType::GetClass`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
