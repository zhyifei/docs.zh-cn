---
title: ICorDebugType::GetClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791300"
---
# <a name="icordebugtypegetclass-method"></a>ICorDebugType::GetClass 方法
获取一个接口指针，该指针指向表示未实例化的泛型类型的 ICorDebugClass。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppClass`  
 弄一个指针，指向表示非实例化泛型类型的 `ICorDebugClass` 接口的地址。  
  
## <a name="remarks"></a>备注  
 只能在某些条件下调用 `GetClass`。 调用[ICorDebugType：： GetType](icordebugtype-gettype-method.md) ，然后调用 `GetClass`。 如果 `ICorDebugType::GetType` 返回 ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE 的 CorElementType 值，则可以调用 `GetClass` 来获取泛型类型的实例化类型。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
