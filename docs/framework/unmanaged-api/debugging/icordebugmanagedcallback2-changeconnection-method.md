---
title: ICorDebugManagedCallback2::ChangeConnection 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: d60644d54373dfb3d1d191900df71d3e5f6547a6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788296"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection 方法
通知调试器与指定连接关联的任务集已更改。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>参数  
 `pProcess`  
 中一个指向 "ICorDebugProcess" 对象的指针，该对象表示包含已更改的连接的进程。  
  
 `dwConnectionId`  
 中已更改的连接的 ID。  
  
## <a name="remarks"></a>备注  
 在以下任一情况下，都将激发 `ChangeConnection` 回调：  
  
- 调试器附加到包含连接的进程时。 在这种情况下，运行时将为进程中的每个连接生成并调度[ICorDebugManagedCallback2：： CreateConnection](icordebugmanagedcallback2-createconnection-method.md)事件和 `ChangeConnection` 事件。 将为每个现有连接生成 `ChangeConnection` 事件，不管该连接的任务集自从创建后是否已更改。  
  
- 当主机在[托管 API](../../../../docs/framework/unmanaged-api/hosting/index.md)中调用[ICLRDebugManager：： SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)时。  
  
 调试器应扫描进程中的所有线程以选取新的更改。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugManagedCallback2 接口](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)
