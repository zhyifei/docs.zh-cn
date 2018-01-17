---
title: "ICorDebugProcess 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess
helpviewer_keywords: ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6fa95d17e7ff6f857765ea2dd48f61b047a47b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess-interface1"></a>ICorDebugProcess 接口 1
表示正在执行托管代码的进程。 此接口是 ICorDebugController 的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ClearCurrentException 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|清除在给定的线程上当前的非托管的异常。|  
|[EnableLogMessages 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|启用和禁用日志消息发送到调试器。|  
|[EnumerateAppDomains 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|枚举中的所有应用程序域的过程。|  
|[EnumerateObjects 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|未实现。|  
|[GetHandle 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|获取进程的句柄。|  
|[GetHelperThreadID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|获取调试器的内部帮助程序线程的操作系统 (OS) 线程 ID。|  
|[GetID 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|获取进程的操作系统 (OS) ID。|  
|[GetObject 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|未实现。|  
|[GetThread 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|获取具有指定的操作系统线程的 ICorDebugThread 实例 id。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|获取给定线程的上下文。|  
|[IsOSSuspended 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|确定线程是否已挂起由于调试器停止进程。|  
|[IsTransitionStub 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|确定是否处于存根，将导致向托管代码转换内的地址。|  
|[ModifyLogSwitch 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|设置指定的日志交换机的严重性级别。|  
|[ReadMemory 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|从进程读取内存。|  
|[SetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|设置给定线程的上下文。|  
|[ThreadForFiberCookie 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|已否决。|  
|[WriteMemory 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|将数据写入的过程中的内存区域。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
