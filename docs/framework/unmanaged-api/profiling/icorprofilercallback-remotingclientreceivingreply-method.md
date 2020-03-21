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
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175130"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="630a2-102">ICorProfilerCallback::RemotingClientReceivingReply 方法</span><span class="sxs-lookup"><span data-stu-id="630a2-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="630a2-103">通知探查器，远程呼叫的服务器端部分已完成，客户端正在接收并即将处理答复。</span><span class="sxs-lookup"><span data-stu-id="630a2-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="630a2-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="630a2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="630a2-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="630a2-106">[在]与[ICorProfiler 回拨](icorprofilercallback-remotingserversendingreply-method.md)中提供的值相对应的值：：在以下条件下重新发送服务器：</span><span class="sxs-lookup"><span data-stu-id="630a2-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="630a2-107">正在激活 GUID Cookie。</span><span class="sxs-lookup"><span data-stu-id="630a2-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="630a2-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="630a2-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="630a2-109">GUID Cookie 在服务器端进程中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="630a2-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="630a2-110">这允许轻松配对远程呼叫。</span><span class="sxs-lookup"><span data-stu-id="630a2-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="630a2-111">[在]`true`如果调用是异步的，则为值;否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="630a2-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="630a2-112">要求</span><span class="sxs-lookup"><span data-stu-id="630a2-112">Requirements</span></span>  
 <span data-ttu-id="630a2-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="630a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="630a2-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="630a2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="630a2-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="630a2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="630a2-116">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="630a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630a2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="630a2-117">See also</span></span>

- [<span data-ttu-id="630a2-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="630a2-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
