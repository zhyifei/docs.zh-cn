---
title: ICorDebugProcess 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b99630ba60cd84254024b91dba9ef9922fd7e041
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943305"
---
# <a name="icordebugprocess-interface"></a>ICorDebugProcess 接口
表示正在执行托管代码的进程。 此接口是 ICorDebugController 的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ClearCurrentException 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|清除给定线程上的当前非托管异常。|  
|[EnableLogMessages 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|启用和禁用向调试器发送日志消息。|  
|[EnumerateAppDomains 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|枚举进程中的所有应用程序域。|  
|[EnumerateObjects 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|未实现。|  
|[GetHandle 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|获取进程的句柄。|  
|[GetHelperThreadID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|获取调试器的内部帮助器线程的操作系统 (OS) 线程 ID。|  
|[GetID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|获取进程的操作系统 (OS) ID。|  
|[GetObject 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|未实现。|  
|[GetThread 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|获取具有指定 OS 线程 ID 的 ICorDebugThread 实例。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|获取给定线程的上下文。|  
|[IsOSSuspended 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|确定线程是否由于调试器停止进程而挂起。|  
|[IsTransitionStub 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|确定地址是否在将导致转换到托管代码的存根内。|  
|[ModifyLogSwitch 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|设置指定的日志开关的严重性级别。|  
|[ReadMemory 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|从进程读取内存。|  
|[SetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|设置给定线程的上下文。|  
|[ThreadForFiberCookie 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|已否决。|  
|[WriteMemory 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|将数据写入进程中的内存区域。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
