---
title: ICorDebugProcess::GetID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ebdf0dd2457cd10e31ff71c32b1c09d0e014431
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765996"
---
# <a name="icordebugprocessgetid-method"></a>ICorDebugProcess::GetID 方法
获取进程的操作系统 (OS) ID。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a>参数  
 `pdwProcessId`  
 [out]进程的唯一 ID。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
