---
title: ICorDebugVariableHome：： GetSlotIndex 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790972"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>ICorDebugVariableHome：： GetSlotIndex 方法
获取本地变量的托管槽索引。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>参数  
 `pSlotIndex`  
 弄指向局部变量的槽索引的指针。  
  
## <a name="return-value"></a>返回值  
 方法返回以下值。  
  
|{2&gt;值&lt;2}|描述|  
|-----------|-----------------|  
|`S_OK`|方法调用在 `pSlotIndex`中返回槽索引值。|  
|`E_FAIL`|当前[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例表示函数参数。|  
  
## <a name="remarks"></a>备注  
 槽索引可用于检索此局部变量的元数据。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugVariableHome 接口](icordebugvariablehome-interface.md)
