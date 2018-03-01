---
title: "ICorDebugVariableHome::GetSlotIndex 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ff62b79fbbb0896941730797473209872e6bfc2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetslotindex-method"></a>ICorDebugVariableHome::GetSlotIndex 方法
获取本地变量的托管的槽索引。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pSlotIndex`  
 [out]指向本地变量的槽索引的指针。  
  
## <a name="return-value"></a>返回值  
 该方法返回以下值。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法调用返回中的槽索引值`pSlotIndex`。|  
|`E_FAIL`|当前[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例表示的函数自变量。|  
  
## <a name="remarks"></a>备注  
 槽索引可用于检索此本地变量的元数据。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugVariableHome 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
