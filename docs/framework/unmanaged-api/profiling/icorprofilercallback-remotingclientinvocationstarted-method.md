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
ms.openlocfilehash: 93bd1010374413f3f4ef7e1424ff8194dded8bb3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866037"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="a7bae-102">ICorProfilerCallback::RemotingClientInvocationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="a7bae-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="a7bae-103">通知探查器已开始远程调用。</span><span class="sxs-lookup"><span data-stu-id="a7bae-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bae-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7bae-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a7bae-105">备注</span><span class="sxs-lookup"><span data-stu-id="a7bae-105">Remarks</span></span>  
 <span data-ttu-id="a7bae-106">此事件对于同步和异步调用是相同的。</span><span class="sxs-lookup"><span data-stu-id="a7bae-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="a7bae-107">以下每对回调都将在同一线程上进行：</span><span class="sxs-lookup"><span data-stu-id="a7bae-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="a7bae-108">`RemotingClientInvocationStarted` 和[ICorProfilerCallback：： RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="a7bae-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="a7bae-109">[ICorProfilerCallback：： RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md)和[ICorProfilerCallback：： RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="a7bae-109">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="a7bae-110">[ICorProfilerCallback：： RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md)和[ICorProfilerCallback：： RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="a7bae-110">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="a7bae-111">应注意远程处理回调的以下问题：</span><span class="sxs-lookup"><span data-stu-id="a7bae-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="a7bae-112">远程处理函数的执行不会由探查器 API 反射，因此无法正确地接收从客户端调用并在服务器上执行的函数的通知。</span><span class="sxs-lookup"><span data-stu-id="a7bae-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="a7bae-113">实际调用是通过代理对象进行的;对于探查器，似乎某些函数是 JIT 编译的，但从未使用过。</span><span class="sxs-lookup"><span data-stu-id="a7bae-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="a7bae-114">探查器不会为异步远程处理事件接收准确的通知。</span><span class="sxs-lookup"><span data-stu-id="a7bae-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7bae-115">需求</span><span class="sxs-lookup"><span data-stu-id="a7bae-115">Requirements</span></span>  
 <span data-ttu-id="a7bae-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7bae-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7bae-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7bae-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7bae-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7bae-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7bae-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7bae-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bae-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7bae-120">See also</span></span>

- [<span data-ttu-id="a7bae-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a7bae-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
