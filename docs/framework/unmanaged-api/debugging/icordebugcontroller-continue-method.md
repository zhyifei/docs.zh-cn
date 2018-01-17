---
title: "ICorDebugController::Continue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Continue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6a96145801aa8ef6482e30e9c00b763d2501f36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue 方法
恢复后调用的托管线程的执行[停止方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fIsOutOfBand`  
 [in]设置为`true`如果继续从带外事件; 否则，设置为`false`。  
  
## <a name="remarks"></a>备注  
 `Continue`在调用后继续执行过程`ICorDebugController::Stop`方法。  
  
 在执行混合模式调试时，请勿调用`Continue`Win32 事件线程除非将继续从带外事件。  
  
 *带内事件*托管的事件或常规的非托管的事件，在此期间，调试器支持与托管状态的过程的交互。 在这种情况下，调试器将接收[icordebugunmanagedcallback:: Debugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)具有回调其`fOutOfBand`参数设置为`false`。  
  
 *的带事件*是在此期间与托管进程状态的交互情况是不可能同时由于事件停止该进程的非托管的事件。 在这种情况下，调试器将接收`ICorDebugUnmanagedCallback::DebugEvent`具有回调其`fOutOfBand`参数设置为`true`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
