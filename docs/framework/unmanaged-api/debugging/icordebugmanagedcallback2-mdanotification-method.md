---
title: ICorDebugManagedCallback2::MDANotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131464"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification 方法
提供一些通知，指出代码执行在要调试的应用程序中遇到了托管调试助手（MDA）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>参数  
 `pController`  
 中指向 ICorDebugController 接口的指针，该接口公开发生 MDA 的进程或应用程序域。  
  
 调试器不应对控制器是进程还是应用程序域作出任何假设，尽管它可以始终查询接口来做出决定。  
  
 `pThread`  
 中指向 ICorDebugThread 接口的指针，该接口公开发生调试事件的托管线程。  
  
 如果在非托管线程上发生 MDA，则 `pThread` 的值将为 null。  
  
 必须从 MDA 对象本身获得操作系统（OS）线程 ID。  
  
 `pMDA`  
 中指向公开 MDA 信息的[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)接口的指针。  
  
## <a name="remarks"></a>备注  
 MDA 是启发式警告，不需要任何显式调试器操作，只需调用[ICorDebugController：： Continue 继续](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)执行正在调试的应用程序。  
  
 公共语言运行时（CLR）可以确定哪些 Mda 被激发，哪些数据在任意时间点处于任意给定的 MDA。 因此，调试器不应生成需要特定 MDA 模式的任何功能。  
  
 Mda 可以排队，并在遇到 MDA 之后立即触发。 如果运行时需要等待到一个安全点来激发 MDA，则会发生这种情况，而不是在遇到 MDA 时激发 MDA。 这也意味着，运行时可能会在一组排队的回调中引发许多 Mda （类似于 "附加" 事件操作）。  
  
 调试器应在从 `MDANotification` 回调返回后立即释放对 `ICorDebugMDA` 实例的引用，以允许 CLR 回收 MDA 使用的内存。 如果激发多个 Mda，则释放实例可以提高性能。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [ICorDebugManagedCallback2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
