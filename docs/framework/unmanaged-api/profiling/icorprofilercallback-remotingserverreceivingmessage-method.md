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
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="d725e-102">ICorProfilerCallback::RemotingServerReceivingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="d725e-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="d725e-103">通知探查器进程已收到远程方法调用或激活请求。</span><span class="sxs-lookup"><span data-stu-id="d725e-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d725e-104">语法</span><span class="sxs-lookup"><span data-stu-id="d725e-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d725e-105">参数</span><span class="sxs-lookup"><span data-stu-id="d725e-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="d725e-106">[in]中提供的值与一个值，将对应[icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="d725e-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="d725e-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d725e-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="d725e-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="d725e-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="d725e-109">GUID cookie 上处于活动状态的客户端过程。</span><span class="sxs-lookup"><span data-stu-id="d725e-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="d725e-110">这样的远程处理调用和逻辑调用堆栈的创建轻松配对。</span><span class="sxs-lookup"><span data-stu-id="d725e-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="d725e-111">[in]一个值，是`true`如果调用的是异步的; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="d725e-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d725e-112">备注</span><span class="sxs-lookup"><span data-stu-id="d725e-112">Remarks</span></span>  
 <span data-ttu-id="d725e-113">如果消息请求是异步的能够使用任意线程将请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="d725e-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d725e-114">惠?</span><span class="sxs-lookup"><span data-stu-id="d725e-114">Requirements</span></span>  
 <span data-ttu-id="d725e-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d725e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d725e-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d725e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d725e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d725e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d725e-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d725e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d725e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d725e-119">See Also</span></span>  
 [<span data-ttu-id="d725e-120">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d725e-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
