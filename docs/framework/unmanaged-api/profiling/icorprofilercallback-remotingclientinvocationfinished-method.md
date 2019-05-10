---
title: ICorProfilerCallback::RemotingClientInvocationFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c3f7c30518184be70c85ff096915738b1633a01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603226"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="2999f-102">ICorProfilerCallback::RemotingClientInvocationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="2999f-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="2999f-103">通知探查器的远程处理调用已在客户端上完成运行。</span><span class="sxs-lookup"><span data-stu-id="2999f-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2999f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2999f-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2999f-105">备注</span><span class="sxs-lookup"><span data-stu-id="2999f-105">Remarks</span></span>  
 <span data-ttu-id="2999f-106">如果远程处理调用是同步的它具有还运行到完成在服务器上。</span><span class="sxs-lookup"><span data-stu-id="2999f-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="2999f-107">如果远程处理调用是异步的回复可能仍应处理在调用时。</span><span class="sxs-lookup"><span data-stu-id="2999f-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="2999f-108">如果预期回复，将出现此问题与调用[icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)额外调用和`RemotingClientInvocationFinished`以指示所需的辅助处理的异步调用。</span><span class="sxs-lookup"><span data-stu-id="2999f-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="2999f-109">以下对回调的每个将发生在同一线程上：</span><span class="sxs-lookup"><span data-stu-id="2999f-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="2999f-110">`RemotingClientInvocationStarted` 和[icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="2999f-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="2999f-111">[Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)和[icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="2999f-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="2999f-112">[Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)和[icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="2999f-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="2999f-113">您应注意以下问题与远程处理回调：</span><span class="sxs-lookup"><span data-stu-id="2999f-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="2999f-114">通过探查器 API，不会反映远程处理函数的执行，因此不会正确接收函数，是从客户端调用，并在服务器上执行的通知。</span><span class="sxs-lookup"><span data-stu-id="2999f-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="2999f-115">实际调用发生通过代理对象;对于探查器，它显示某些函数是 JIT 编译，但永远不会使用。</span><span class="sxs-lookup"><span data-stu-id="2999f-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="2999f-116">探查器不会接收异步远程处理事件的准确通知。</span><span class="sxs-lookup"><span data-stu-id="2999f-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2999f-117">要求</span><span class="sxs-lookup"><span data-stu-id="2999f-117">Requirements</span></span>  
 <span data-ttu-id="2999f-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2999f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2999f-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2999f-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2999f-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2999f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2999f-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2999f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2999f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2999f-122">See also</span></span>

- [<span data-ttu-id="2999f-123">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2999f-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
