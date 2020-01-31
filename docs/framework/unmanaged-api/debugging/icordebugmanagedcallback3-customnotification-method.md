---
title: ICorDebugManagedCallback3::CustomNotification 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 078f90387a475559067d402610ec264f4076ae01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793256"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>ICorDebugManagedCallback3::CustomNotification 方法
指示已引发自定义调试器通知。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a>参数  
 `pThread`  
 中指向引发通知的线程的指针。  
  
 `pAppDomain`  
 中一个指针，指向包含引发通知的线程的应用程序域。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法成功完成。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 对[ICorDebugThread4：： GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md)方法的后续调用检索传递到 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 方法的线程对象。 线程对象的类型必须以前已通过调用[ICorDebugProcess3：： SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md)方法启用。 调试器可以从 thread 对象的字段中读取特定于类型的参数，并可以将响应存储在字段中。  
  
 [ICorDebug](icordebug-interface.md)接口不对通知类型或其内容施加任何策略，并且通知的语义严格地是调试器、应用程序和 .NET Framework 之间的协定。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugManagedCallback3 接口](icordebugmanagedcallback3-interface.md)
- [调试接口](debugging-interfaces.md)
- [调试](index.md)
