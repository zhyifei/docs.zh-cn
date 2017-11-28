---
title: "ICorDebugValue3::GetSize64 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3::GetSize64
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b129ebe666972052775c2c3e44e38bb6a25a176e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64 方法
获取以字节为单位，此大小， [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 pSize  
 [out]指向的大小，以字节为单位，此对象的指针。  
  
## <a name="remarks"></a>备注  
 如果此值的类型是引用类型，此方法将返回指针的大小，而不是对象的大小。  
  
 `ICorDebugValue3::GetSize`方法不同于[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)其输出参数的类型中的方法。 在[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)，输出参数是`ULONG32`; 在`ICorDebugValue3::GetSize`，它是`ULONG64`。 这使[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)接口报告的大小超过 2 GB 的数组。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugValue3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
