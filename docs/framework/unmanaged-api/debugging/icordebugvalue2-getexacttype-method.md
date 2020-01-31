---
title: ICorDebugValue2::GetExactType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 6c5e5d1c9f734e097fc9e871d7a0cffdc9bb9138
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791125"
---
# <a name="icordebugvalue2getexacttype-method"></a>ICorDebugValue2::GetExactType 方法
获取一个接口指针，该指针指向表示此值 <xref:System.Type> 的 "ICorDebugType" 对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppType`  
 弄指向 `ICorDebugType` 对象的地址的指针，该对象表示此 "ICorDebugValue2" 对象表示的值的 <xref:System.Type>。  
  
## <a name="remarks"></a>备注  
 泛型感知 `GetExactType` 方法取代了[ICorDebugObjectValue：： GetClass](icordebugobjectvalue-getclass-method.md)和[ICorDebugValue：： GetType](icordebugvalue-gettype-method.md)方法，其中每个方法都返回值类型的相关信息。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅
