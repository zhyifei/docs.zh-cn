---
title: "ICorDebugManagedCallback3::CustomNotification 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c42443b0d1e355d4233909357c341763298160e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>ICorDebugManagedCallback3::CustomNotification 方法
指示已引发的自定义调试器通知。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a>参数  
 `pThread`  
 [in]指向引发通知的线程的指针。  
  
 `pAppDomain`  
 [in]指向包含线程引发通知的应用程序域的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 后续调用[icordebugthread4:: Getcurrentcustomdebuggernotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)方法检索传递给使线程对象<xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>方法。 线程对象的类型必须之前已启用通过调用[icordebugprocess3:: Setenablecustomnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)方法。 调试器可以读取的线程对象，字段的特定类型的参数，并且可以存储到字段的响应。  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)接口有一定的通知或其内容的类型上没有策略和通知的语义仅限调试器，应用程序和.NET Framework 之间的协定。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugManagedCallback3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
