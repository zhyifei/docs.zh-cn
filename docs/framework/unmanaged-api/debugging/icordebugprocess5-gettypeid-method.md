---
title: ICorDebugProcess5::GetTypeID 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07c23a32037e83a878bb3136c48176f19249b207
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173182"
---
# <a name="icordebugprocess5gettypeid-method"></a>ICorDebugProcess5::GetTypeID 方法
将转换的对象地址[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a>参数  
 `obj`  
 [in]对象的地址。  
  
 `pId`  
 一个指向[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识的对象的值。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugProcess5 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
