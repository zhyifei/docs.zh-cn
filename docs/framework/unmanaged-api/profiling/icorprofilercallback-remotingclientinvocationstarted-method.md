---
title: ICorProfilerCallback::RemotingClientInvocationStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bec96ef50416d946b1f12fd503e04f976ca58f1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662934"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="f14dc-102">ICorProfilerCallback::RemotingClientInvocationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="f14dc-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="f14dc-103">通知探查器已启动的远程处理调用。</span><span class="sxs-lookup"><span data-stu-id="f14dc-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="f14dc-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f14dc-105">备注</span><span class="sxs-lookup"><span data-stu-id="f14dc-105">Remarks</span></span>  
 <span data-ttu-id="f14dc-106">此事件是相同的同步和异步调用。</span><span class="sxs-lookup"><span data-stu-id="f14dc-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="f14dc-107">以下对回调的每个将发生在同一线程上：</span><span class="sxs-lookup"><span data-stu-id="f14dc-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="f14dc-108">`RemotingClientInvocationStarted` 和[icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="f14dc-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="f14dc-109">[Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)和[icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="f14dc-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="f14dc-110">[Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)和[icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="f14dc-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="f14dc-111">您应注意以下问题与远程处理回调：</span><span class="sxs-lookup"><span data-stu-id="f14dc-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="f14dc-112">通过探查器 API，不会反映远程处理函数的执行，因此不会正确接收函数，是从客户端调用，并在服务器上执行的通知。</span><span class="sxs-lookup"><span data-stu-id="f14dc-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="f14dc-113">实际调用发生通过代理对象;对于探查器，它显示某些函数是 JIT 编译，但永远不会使用。</span><span class="sxs-lookup"><span data-stu-id="f14dc-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="f14dc-114">探查器不会接收异步远程处理事件的准确通知。</span><span class="sxs-lookup"><span data-stu-id="f14dc-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f14dc-115">要求</span><span class="sxs-lookup"><span data-stu-id="f14dc-115">Requirements</span></span>  
 <span data-ttu-id="f14dc-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f14dc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f14dc-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f14dc-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f14dc-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f14dc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f14dc-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f14dc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14dc-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f14dc-120">See also</span></span>

- [<span data-ttu-id="f14dc-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f14dc-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
