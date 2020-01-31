---
title: ICorDebugProcess::SetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 66d544bbc0511ea76565376c8f10294f1758026b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792573"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext 方法
设置此进程中给定线程的上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>参数  
 `threadID`  
 中要为其设置上下文的线程的 ID。  
  
 `contextSize`  
 [in] `context` 数组的大小。  
  
 `context`  
 中用于描述线程上下文的字节数组。  
  
 上下文指定正在执行线程的处理器的体系结构。  
  
## <a name="remarks"></a>备注  
 调试器应调用此方法而不是 Win32 `SetThreadContext` 函数，因为该线程实际可能处于 "被劫持" 状态，在该状态下，其上下文已暂时发生更改。 仅当线程在本机代码中时，才应使用此方法。 在托管代码中对线程使用[ICorDebugRegisterSet](icordebugregisterset-interface.md) 。 在带外（OOB）调试事件期间，你永远不需要修改线程的上下文。  
  
 传递的数据必须是当前平台的上下文结构。  
  
 如果使用不当，此方法可能会损坏运行时。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
