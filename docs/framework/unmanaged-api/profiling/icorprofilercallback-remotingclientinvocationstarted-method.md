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
ms.openlocfilehash: 5de291774f1e20b4c399c416f9f52657fa8a9a84
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445824"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="c6c02-102">ICorProfilerCallback::RemotingClientInvocationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="c6c02-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="c6c02-103">通知探查器已开始远程调用。</span><span class="sxs-lookup"><span data-stu-id="c6c02-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c02-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6c02-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c6c02-105">备注</span><span class="sxs-lookup"><span data-stu-id="c6c02-105">Remarks</span></span>  
 <span data-ttu-id="c6c02-106">此事件对于同步和异步调用是相同的。</span><span class="sxs-lookup"><span data-stu-id="c6c02-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="c6c02-107">以下每对回调都将在同一线程上进行：</span><span class="sxs-lookup"><span data-stu-id="c6c02-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="c6c02-108">`RemotingClientInvocationStarted` 和[ICorProfilerCallback：： RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="c6c02-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="c6c02-109">[ICorProfilerCallback：： RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)和[ICorProfilerCallback：： RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="c6c02-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="c6c02-110">[ICorProfilerCallback：： RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)和[ICorProfilerCallback：： RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="c6c02-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="c6c02-111">应注意远程处理回调的以下问题：</span><span class="sxs-lookup"><span data-stu-id="c6c02-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="c6c02-112">远程处理函数的执行不会由探查器 API 反射，因此无法正确地接收从客户端调用并在服务器上执行的函数的通知。</span><span class="sxs-lookup"><span data-stu-id="c6c02-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="c6c02-113">实际调用是通过代理对象进行的;对于探查器，似乎某些函数是 JIT 编译的，但从未使用过。</span><span class="sxs-lookup"><span data-stu-id="c6c02-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="c6c02-114">探查器不会为异步远程处理事件接收准确的通知。</span><span class="sxs-lookup"><span data-stu-id="c6c02-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c02-115">要求</span><span class="sxs-lookup"><span data-stu-id="c6c02-115">Requirements</span></span>  
 <span data-ttu-id="c6c02-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c02-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c02-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6c02-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6c02-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6c02-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6c02-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c02-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c02-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6c02-120">See also</span></span>

- [<span data-ttu-id="c6c02-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c6c02-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
