---
title: ICorDebugVariableHome::GetOffset 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 687c3bb441c2a12529c873b4fa5f9283b9326a40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659064"
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome::GetOffset 方法
获取从基寄存器变量的偏移量。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pOffset`  
 [out]从基寄存器的偏移量。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下值：  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|该变量是在寄存器相对内存位置。|  
|`E_FAIL`|变量不是在寄存器相对内存位置。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugVariableHome 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
