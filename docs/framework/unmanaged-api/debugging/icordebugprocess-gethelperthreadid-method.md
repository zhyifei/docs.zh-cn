---
title: "ICorDebugProcess::GetHelperThreadID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 092e99cb1d5534cee56db08b5a2eedaaa2fc4724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID 方法
获取调试器的内部帮助程序线程的操作系统 (OS) 线程 ID。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pThreadID`  
 [out]指向操作系统线程的调试器的内部帮助程序线程的 ID。  
  
## <a name="remarks"></a>备注  
 托管和非托管在调试期间，它将由调试器的负责确保具有指定 ID 的线程保持运行，如果它达到由调试器放置一个断点。 调试器还可能想要隐藏用户此线程。 如果没有帮助程序线程存在于进程中尚未，`GetHelperThreadID`方法返回零 *`pThreadID`。  
  
 无法缓存帮助程序线程的线程 ID，因为它可能会随着时间的推移进行更改。 你必须重新查询每次发生停止事件的线程 ID。  
  
 将调试器的帮助程序线程的线程 ID 将正确上每个非托管[icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)事件，从而允许调试器来确定其帮助程序线程的线程 ID 和隐藏用户。 在非托管过程标识为帮助程序线程的线程`ICorDebugManagedCallback::CreateThread`事件将永远不会运行托管的用户代码。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl。 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
