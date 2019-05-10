---
title: ICorProfilerCallback::RemotingClientSendingMessage 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62c2774701b0bb4bc322d689fec43e312bc776a3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662906"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a>ICorProfilerCallback::RemotingClientSendingMessage 方法
通知探查器客户端向服务器发送请求。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>参数  
 `pCookie`  
 [in]使用中提供的值相对应的值[icorprofilercallback:: Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)在这些情况下：  
  
- 远程处理 GUID cookie 处于活动状态。  
  
- 通道成功传输消息。  
  
- GUID cookie 处于活动状态的服务器端的过程。  
  
 这允许轻松配对的远程处理调用以及逻辑调用堆栈的创建。  
  
 `fIsAsync`  
 [in]一个值，则该值`true`的调用是异步的; 否则为如果`false`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
