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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cde75f1f33df83131212b0f7d4b349b20338f3dd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662875"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="1c47b-102">ICorProfilerCallback::RemotingServerSendingReply 方法</span><span class="sxs-lookup"><span data-stu-id="1c47b-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="1c47b-103">通知探查器进程已完成处理远程方法调用请求，并将要通过通道答复传输。</span><span class="sxs-lookup"><span data-stu-id="1c47b-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c47b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c47b-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c47b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c47b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="1c47b-106">[in]指向将与中提供的值相对应的 GUID 的指针[icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="1c47b-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="1c47b-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1c47b-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="1c47b-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="1c47b-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="1c47b-109">GUID cookie 处于活动状态的客户端的过程。</span><span class="sxs-lookup"><span data-stu-id="1c47b-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="1c47b-110">这允许轻松配对的远程处理调用以及逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="1c47b-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="1c47b-111">[in]一个值，则该值`true`的调用是异步的; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="1c47b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c47b-112">要求</span><span class="sxs-lookup"><span data-stu-id="1c47b-112">Requirements</span></span>  
 <span data-ttu-id="1c47b-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c47b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c47b-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c47b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c47b-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c47b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c47b-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c47b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c47b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c47b-117">See also</span></span>

- [<span data-ttu-id="1c47b-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1c47b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
