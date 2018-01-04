---
title: "ICorProfilerCallback::RemotingClientInvocationStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 071e2892202271cac5e0acb226e9bef0e626b134
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="b9f36-102">ICorProfilerCallback::RemotingClientInvocationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="b9f36-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="b9f36-103">通知探查器已启动的远程处理调用。</span><span class="sxs-lookup"><span data-stu-id="b9f36-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f36-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9f36-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b9f36-105">备注</span><span class="sxs-lookup"><span data-stu-id="b9f36-105">Remarks</span></span>  
 <span data-ttu-id="b9f36-106">此事件是相同的同步和异步调用。</span><span class="sxs-lookup"><span data-stu-id="b9f36-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="b9f36-107">每个回调的以下对会在同一线程上发生:</span><span class="sxs-lookup"><span data-stu-id="b9f36-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="b9f36-108">`RemotingClientInvocationStarted`和[icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="b9f36-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="b9f36-109">[Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)和[icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="b9f36-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="b9f36-110">[Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)和[icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="b9f36-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="b9f36-111">你应注意的远程处理回调以下问题：</span><span class="sxs-lookup"><span data-stu-id="b9f36-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="b9f36-112">事件探查器 API，不会反映远程处理函数执行，以便正确未收到通知，会从客户端调用在服务器上执行的函数。</span><span class="sxs-lookup"><span data-stu-id="b9f36-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="b9f36-113">实际调用是通过代理对象;对于探查器，它显示某些函数是 JIT 编译，但从未使用。</span><span class="sxs-lookup"><span data-stu-id="b9f36-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="b9f36-114">探查器不接收异步远程处理事件的准确通知。</span><span class="sxs-lookup"><span data-stu-id="b9f36-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f36-115">惠?</span><span class="sxs-lookup"><span data-stu-id="b9f36-115">Requirements</span></span>  
 <span data-ttu-id="b9f36-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9f36-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f36-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9f36-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9f36-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9f36-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9f36-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f36-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f36-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9f36-120">See Also</span></span>  
 [<span data-ttu-id="b9f36-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b9f36-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
