---
title: ICorDebug::SetManagedHandler 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 54ef1cab27a39de39b39996729be6b8160570745
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788973"
---
# <a name="icordebugsetmanagedhandler-method"></a>ICorDebug::SetManagedHandler 方法
指定托管事件的事件处理程序对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>参数  
 `pCallback`  
 中指向[ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)对象的指针，该对象为事件处理程序对象。  
  
## <a name="remarks"></a>备注  
 必须在创建时调用 `SetManagedHandler`。  
  
 如果 `ICorDebugManagedCallback` 实现未包含足够的接口来处理要调试的应用程序的调试事件，`SetManagedHandler` 将返回 E_NOINTERFACE 的 HRESULT。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebug 接口](icordebug-interface.md)
