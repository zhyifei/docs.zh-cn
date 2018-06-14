---
title: ICorDebugController::Stop 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cd0fc9f86515d63533275002301eb47f11feebb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411261"
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop 方法
在进程中运行托管的代码的所有线程上执行协作停止。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwTimeoutIgnored`  
 未使用。  
  
## <a name="remarks"></a>备注  
 `Stop` 在进程中执行的协作停止运行的所有线程上托管代码。 仅托管调试会话期间，非托管的线程可能会继续运行 （但在尝试调用托管的代码时会被阻止）。 互操作调试会话，在非托管的线程也会停止。 `dwTimeoutIgnored`值是当前忽略并且视为 INFINITE (-1)。 如果协作停止失败。 由于死锁，所有线程均会都挂起，并返回 E_TIMEOUT。  
  
> [!NOTE]
>  `Stop` 是调试 API 中的仅同步方法。 当`Stop`返回 S_OK，进程已停止。 不执行回调提供通知停止点的侦听器。 调试器必须调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)以允许恢复的过程。  
  
 调试器维护停止计数器。 在计数器变为零时，控制器将继续运行。 每次调用`Stop`或每次调度的回调递增的计数器。 每次调用`ICorDebugController::Continue`递减计数器。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
