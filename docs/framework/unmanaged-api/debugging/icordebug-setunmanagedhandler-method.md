---
title: ICorDebug::SetUnmanagedHandler 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: cafa1c99a8988c199d866796911d1983aabb7208
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785068"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler 方法
指定非托管事件的事件处理程序对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>参数  
 `pCallback`  
 中指向[ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)对象的指针，该对象表示非托管事件的事件处理程序。  
  
## <a name="remarks"></a>备注  
 非托管事件的事件处理程序对象必须在调用[ICorDebug：： Initialize](icordebug-initialize-method.md)之后以及对[ICorDebug：： CreateProcess](icordebug-createprocess-method.md)或[ICorDebug：:D ebugactiveprocess](icordebug-debugactiveprocess-method.md)的任何调用之前设置。 但出于传统目的，在引发第一个本机调试事件之前，不需要为非托管事件设置事件处理程序对象。 具体来说，如果 `ICorDebug::CreateProcess` 设置 CREATE_SUSPENDED 标志，则在主线程恢复之前，不能调度本机调试事件。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebug 接口](icordebug-interface.md)
