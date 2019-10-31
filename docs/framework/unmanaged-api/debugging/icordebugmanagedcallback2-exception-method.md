---
title: ICorDebugManagedCallback2::Exception 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: f40030a2034057e83de51a21655a686f30b9ee88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137446"
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception 方法
通知调试器已开始搜索异常处理程序。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `pAppDomain`  
 中指向 ICorDebugAppDomain 对象的指针，该对象表示包含引发异常的线程的应用程序域。  
  
 `pThread`  
 中指向 ICorDebugThread 对象的指针，该对象表示引发异常的线程。  
  
 `pFrame`  
 中指向 ICorDebugFrame 对象的指针，该对象表示一个帧，由 `dwEventType` 参数确定。 有关详细信息，请参阅 "备注" 部分中的表。  
  
 `nOffset`  
 中一个整数，指定由 `dwEventType` 参数确定的偏移量。 有关详细信息，请参阅 "备注" 部分中的表。  
  
 `dwEventType`  
 中CorDebugExceptionCallbackType 枚举的一个值，该值指定此异常回调的类型。  
  
 `dwFlags`  
 中[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)枚举的一个值，该值指定有关异常的其他信息  
  
## <a name="remarks"></a>备注  
 在异常处理过程的搜索阶段，会在不同的点调用 `Exception` 回调。 也就是说，可以在展开异常时多次调用它。  
  
 可以从 `pThread` 参数所引用的 ICorDebugThread 对象中检索正在处理的异常。  
  
 特定的帧和偏移由 `dwEventType` 参数确定，如下所示：  
  
|`dwEventType` 的值|`pFrame` 的值|`nOffset` 的值|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|引发异常的帧。|帧中的指令指针。|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|最接近引发的异常点的用户代码框架。|帧中的指令指针。|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|包含 catch 处理程序的帧。|Catch 处理程序开头的 Microsoft 中间语言（MSIL）偏移量。|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|尚未.|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugManagedCallback2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
