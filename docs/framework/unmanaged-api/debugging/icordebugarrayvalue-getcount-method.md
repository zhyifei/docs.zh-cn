---
title: ICorDebugArrayValue::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e45f49d17a5b71abfb58ff8c0126abad49322c5b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737587"
---
# <a name="icordebugarrayvaluegetcount-method"></a>ICorDebugArrayValue::GetCount 方法
获取数组中的元素总数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a>参数  
 `pnCount`  
 [out]指向数组中的元素总数的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
