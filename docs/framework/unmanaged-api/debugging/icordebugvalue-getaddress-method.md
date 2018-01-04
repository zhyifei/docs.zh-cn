---
title: "ICorDebugValue::GetAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8aa5a0c3740b6cf97d2a5d855343a36b90fd538
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetaddress-method"></a>ICorDebugValue::GetAddress 方法
获取此"ICorDebugValue"对象，它是正在调试的过程中的地址。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [out]指向`CORDB_ADDRESS`对象，它指定此值对象的地址。  
  
## <a name="remarks"></a>备注  
 如果值为不可用，则返回 0 （零）。 此值是寄存器中至少一部分时可能发生或存储在垃圾回收器句柄 (`GCHandle`)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
