---
title: ICorDebugVariableHome::GetArgumentIndex 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163704bf9a71ceda04bdfd73f9ca676c19d8a62c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526635"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>ICorDebugVariableHome::GetArgumentIndex 方法
获取函数参数的索引。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pArgumentIndex`  
 [out]指向参数索引的指针。  
  
## <a name="return-value"></a>返回值  
 该方法返回以下值。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法调用返回了有效的参数索引。|  
|`E_FAIL`|当前[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例表示的本地变量。|  
  
## <a name="remarks"></a>备注  
 可以使用的参数索引检索此参数的元数据。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugVariableHome 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
