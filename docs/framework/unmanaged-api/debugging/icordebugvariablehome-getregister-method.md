---
title: "ICorDebugVariableHome::GetRegister 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f16e4bfe4767e1b49d7dacf0481e8911a90e178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome::GetRegister 方法
获取包含的位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRegister`  
 [out]CorDebugRegister 枚举值，该值指示与位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。  
  
## <a name="return-value"></a>返回值  
 该方法返回以下值：  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|变量是在由寄存器中`pRegister`自变量。|  
|`E_FAIL`|该变量不是在注册或注册相对位置。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [VariableLocationType 枚举](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [ICorDebugVariableHome 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
