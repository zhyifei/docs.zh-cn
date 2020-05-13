---
title: ICorDebugManagedCallback::ControlCTrap 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: 33a68d11a8d17e46533b4f83bbf87aafe171e612
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212394"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a>ICorDebugManagedCallback::ControlCTrap 方法
通知调试器在被调试的进程中捕获了 CTRL + C。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>参数  
 `pProcess`  
 中指向 ICorDebugProcess 对象的指针，该对象表示在其中捕获 CTRL + C 的进程。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|调试器将处理 CTRL + C 陷阱。|  
|S_FALSE|调试器将不会处理 CTRL + C 陷阱。|  
  
## <a name="remarks"></a>备注  
 此回调的进程中的所有应用程序域都已停止。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)
