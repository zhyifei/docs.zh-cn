---
title: ICorDebugThread::GetID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11e21e913e4749705ba6c7f91016be21b4de1712
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769964"
---
# <a name="icordebugthreadgetid-method"></a>ICorDebugThread::GetID 方法
获取此 ICorDebugThread 的活动部分的当前操作系统标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a>参数  
 `pdwThreadId`  
 [out]线程的标识符。  
  
## <a name="remarks"></a>备注  
 操作系统识别符的过程中，执行过程中可能会更改，并且可以在线程的不同部分的不同值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
