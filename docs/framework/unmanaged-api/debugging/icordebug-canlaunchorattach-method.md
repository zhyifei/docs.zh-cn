---
title: "ICorDebug::CanLaunchOrAttach 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CanLaunchOrAttach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5bd657c73dfaf7643405b4b657edeffa6e33cd68
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach 方法
返回一个 HRESULT，指示是否可以在当前的计算机和运行时配置的上下文中启动新的进程或附加到指定的现有进程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwProcessId`  
 [in]现有的进程 ID。  
  
 `win32DebuggingEnabled`  
 [in]传入`true`如果打算使用 Win32 调试启用，启动的虚拟机或模板，若要使用 Win32 调试启用的; 否则为附加传递`false`。  
  
## <a name="return-value"></a>返回值  
 如果调试服务确定启动新的进程或附加到给定的进程，则为 S_OK 是有可能，提供有关当前的计算机和运行时配置的信息。 可能的 HRESULT 值有：  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>备注  
 此方法是仅用于提供信息。 接口不会停止你启动和附加到进程，而不考虑值返回的`CanLaunchOrAttach`。  
  
 如果你打算使用 Win32 调试启用启动或使用 Win32 调试启用附加，则传递`true`为`win32DebuggingEnabled`。 通过返回的 HRESULT`CanLaunchOrAttach`可能会与不同，如果使用此选项。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
