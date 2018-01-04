---
title: "ICorDebugManagedCallback::ExitProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7be74520fff65b113f54d82305a84dd183286876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess 方法
通知调试器进程已退出。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pProcess`  
 [in]指向 ICorDebugProcess 对象表示进程的指针。  
  
## <a name="remarks"></a>备注  
 无法继续从`ExitProcess`事件。 过程似乎已停止时，此事件可能与其他事件以异步方式进行激发。 发生这种情况在进程终止时停止，通常是由于某种外部因素。  
  
 如果公共语言运行时 (CLR) 已经在调度托管的回调，将会延迟此事件，直到该回调返回。  
  
 `ExitProcess`事件是保证获取关闭时调用的唯一退出/卸载事件。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
