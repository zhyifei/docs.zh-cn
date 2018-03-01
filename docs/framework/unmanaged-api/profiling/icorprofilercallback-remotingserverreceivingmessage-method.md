---
title: "ICorProfilerCallback::RemotingServerReceivingMessage 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4542f5362d83bc5c0419b9f1ff389c9a21aad29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>ICorProfilerCallback::RemotingServerReceivingMessage 方法
通知探查器进程已收到远程方法调用或激活请求。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>参数  
 `pCookie`  
 [in]中提供的值与一个值，将对应[icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)在这些情况下：  
  
-   远程处理 GUID cookie 处于活动状态。  
  
-   通道成功传输消息。  
  
-   GUID cookie 上处于活动状态的客户端过程。  
  
 这样的远程处理调用和逻辑调用堆栈的创建轻松配对。  
  
 `fIsAsync`  
 [in]一个值，是`true`如果调用的是异步的; 否则为`false`。  
  
## <a name="remarks"></a>备注  
 如果消息请求是异步的能够使用任意线程将请求提供服务。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
