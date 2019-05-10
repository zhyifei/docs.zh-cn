---
title: ICorProfilerCallback::RemotingClientReceivingReply 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2134a7f12ac482b3fe79ac722684ac8601a7280b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662920"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="ce84f-102">ICorProfilerCallback::RemotingClientReceivingReply 方法</span><span class="sxs-lookup"><span data-stu-id="ce84f-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="ce84f-103">通知探查器的远程处理调用的服务器端部分已完成，而客户端正在接收并即将处理回复。</span><span class="sxs-lookup"><span data-stu-id="ce84f-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce84f-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce84f-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ce84f-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce84f-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="ce84f-106">[in]中提供的值的值将对应[icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="ce84f-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="ce84f-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ce84f-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="ce84f-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="ce84f-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="ce84f-109">GUID cookie 处于活动状态的服务器端的过程。</span><span class="sxs-lookup"><span data-stu-id="ce84f-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="ce84f-110">这允许轻松配对的远程处理调用。</span><span class="sxs-lookup"><span data-stu-id="ce84f-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ce84f-111">[in]一个值，则该值`true`的调用是异步的; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="ce84f-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce84f-112">要求</span><span class="sxs-lookup"><span data-stu-id="ce84f-112">Requirements</span></span>  
 <span data-ttu-id="ce84f-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce84f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce84f-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce84f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce84f-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce84f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce84f-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce84f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce84f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce84f-117">See also</span></span>

- [<span data-ttu-id="ce84f-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ce84f-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
