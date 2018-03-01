---
title: "ICorDebugProcess5::GetTypeForTypeID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4678575dba6210dc8c97f8ed18d5ded208a5c74e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5gettypefortypeid-method"></a>ICorDebugProcess5::GetTypeForTypeID 方法
将转换为 ICorDebugType 值类型标识符。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 [in]类型标识符中。  
  
 `ppType`  
 [out]指向 ICorDebugType 对象的地址的指针。  
  
## <a name="remarks"></a>备注  
 在某些情况下，返回类型标识符的方法可能返回 null`COR_TYPEID`值。 如果此值作为传递`id`自变量，`GetTypeForTypeID`方法将失败并返回`E_FAIL`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugProcess5 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
