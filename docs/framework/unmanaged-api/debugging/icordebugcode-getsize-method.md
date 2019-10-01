---
title: ICorDebugCode::GetSize 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89df0e9be0600b51dcc8a68c5aba3f06e86e1b53
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700804"
---
# <a name="icordebugcodegetsize-method"></a>ICorDebugCode::GetSize 方法

获取此 "ICorDebugCode" 表示的二进制代码的大小（以字节为单位）。

## <a name="syntax"></a>语法

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a>Parameters

 `pcBytes`  
 弄一个指针，指向此 @no__t 0 对象表示的二进制代码的大小（以字节为单位）。

## <a name="requirements"></a>要求

 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。

 **标头：** Cordebug.idl，Cordebug.idl

 **类库**CorGuids.lib

 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
 
