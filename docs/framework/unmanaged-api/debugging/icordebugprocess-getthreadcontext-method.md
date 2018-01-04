---
title: "ICorDebugProcess::GetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e45d101db946747463ba4200bc5dd3b95d21391
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext 方法
获取此进程中给定的线程的上下文。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>参数  
 `threadID`  
 [in]为其检索上下文线程的 ID。  
  
 `contextSize`  
 [in] `context` 数组的大小。  
  
 `context`  
 [在中，out]描述线程的上下文的字节数组。  
  
 上下文指定在其执行线程的处理器的体系结构。  
  
## <a name="remarks"></a>备注  
 调试器应调用此方法，而不是 Win32`GetThreadContext`方法，因为该线程可能实际上处于"被劫持"状态，在其中其上下文已被暂时更改。 只有当线程处于本机代码时，应使用此方法。 使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)托管代码中的线程。  
  
 返回的数据是当前平台的上下文结构。 只需与 Win32`GetThreadContext`方法中，调用方应初始化`context`之前调用此方法的参数。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
