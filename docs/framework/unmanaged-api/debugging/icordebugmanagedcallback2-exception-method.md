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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faefff879142d66c4c596f1b30a25e349a4014b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception 方法
通知调试器搜索异常处理程序已开始。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAppDomain`  
 [in]指向一个表示包含引发异常的线程的应用程序域的 ICorDebugAppDomain 对象的指针。  
  
 `pThread`  
 [in]指向一个 ICorDebugThread 对象，表示引发异常的线程的指针。  
  
 `pFrame`  
 [in]指向根据所表示的帧，ICorDebugFrame 对象的指针`dwEventType`参数。 有关详细信息，请参阅备注部分中的表。  
  
 `nOffset`  
 [in]一个整数，指定偏移量，所确定的那样`dwEventType`参数。 有关详细信息，请参阅备注部分中的表。  
  
 `dwEventType`  
 [in]CorDebugExceptionCallbackType 枚举，指定此异常回调的类型的值。  
  
 `dwFlags`  
 [in]值为[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)枚举，它指定有关异常的其他信息  
  
## <a name="remarks"></a>备注  
 `Exception`异常处理过程的搜索阶段在不同时刻调用回调。 即，它可以调用多个一次而展开异常。  
  
 正在处理的异常可以从所引用的 ICorDebugThread 对象检索`pThread`参数。  
  
 由特定帧和偏移量`dwEventType`参数，如下所示：  
  
|`dwEventType` 的值|`pFrame` 的值|`nOffset` 的值|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|引发异常的帧。|指令指针的帧中。|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|引发的异常点最接近的用户代码帧。|指令指针的帧中。|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|包含 catch 处理程序的帧。|Catch 处理程序的开头的 Microsoft 中间语言 (MSIL) 偏移量。|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|未定义。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugManagedCallback2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
