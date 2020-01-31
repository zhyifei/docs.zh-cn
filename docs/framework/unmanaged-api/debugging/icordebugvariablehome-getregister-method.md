---
title: ICorDebugVariableHome：： GetRegister 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790978"
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome：： GetRegister 方法
获取一个寄存器，其中包含位置类型为 `VLT_REGISTER`的变量，以及位置类型为 `VLT_REGISTER_RELATIVE`的变量的基寄存器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>参数  
 `pRegister`  
 弄一个 CorDebugRegister 枚举值，该值指示注册位置类型为 `VLT_REGISTER`的变量，并使用 `VLT_REGISTER_RELATIVE`位置类型的变量的基寄存器。  
  
## <a name="return-value"></a>返回值  
 方法返回以下值：  
  
|{2&gt;值&lt;2}|描述|  
|-----------|-----------------|  
|`S_OK`|变量位于 `pRegister` 参数所指示的寄存器中。|  
|`E_FAIL`|变量不在寄存器或寄存器相对位置中。|  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [VariableLocationType 枚举](variablelocationtype-enumeration.md)
- [ICorDebugVariableHome 接口](icordebugvariablehome-interface.md)
