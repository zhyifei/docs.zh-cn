---
title: ICorProfilerCallback::RemotingServerSendingReply 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: f77901623ef4df7b43276c18a910cf62fcc4451d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865969"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="88831-102">ICorProfilerCallback::RemotingServerSendingReply 方法</span><span class="sxs-lookup"><span data-stu-id="88831-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="88831-103">通知探查器进程已处理完远程方法调用请求，即将通过通道传输答复。</span><span class="sxs-lookup"><span data-stu-id="88831-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88831-104">语法</span><span class="sxs-lookup"><span data-stu-id="88831-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88831-105">参数</span><span class="sxs-lookup"><span data-stu-id="88831-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="88831-106">中指向 GUID 的指针，该 GUID 将与以下条件下的[ICorProfilerCallback：： RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md)中提供的值相对应：</span><span class="sxs-lookup"><span data-stu-id="88831-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="88831-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="88831-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="88831-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="88831-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="88831-109">GUID cookie 在客户端进程中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="88831-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="88831-110">这样就可以轻松地配对远程调用和逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="88831-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="88831-111">中如果调用是异步的，则为 `true` 的值;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="88831-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88831-112">需求</span><span class="sxs-lookup"><span data-stu-id="88831-112">Requirements</span></span>  
 <span data-ttu-id="88831-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88831-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88831-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88831-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88831-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88831-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88831-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88831-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88831-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88831-117">See also</span></span>

- [<span data-ttu-id="88831-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="88831-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
