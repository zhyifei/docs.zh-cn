---
title: ICorProfilerCallback::RemotingServerReceivingMessage 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67ec3bf10638538b49f1ec44ff583bdf4ba4ef9e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572248"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="6821b-102">ICorProfilerCallback::RemotingServerReceivingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="6821b-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="6821b-103">通知探查器进程已接收到的远程方法调用或激活请求。</span><span class="sxs-lookup"><span data-stu-id="6821b-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6821b-104">语法</span><span class="sxs-lookup"><span data-stu-id="6821b-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6821b-105">参数</span><span class="sxs-lookup"><span data-stu-id="6821b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="6821b-106">[in]中提供的值的值将对应[icorprofilercallback:: Remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="6821b-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="6821b-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="6821b-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="6821b-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="6821b-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="6821b-109">GUID cookie 处于活动状态的客户端的过程。</span><span class="sxs-lookup"><span data-stu-id="6821b-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="6821b-110">这允许轻松配对的远程处理调用以及逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="6821b-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="6821b-111">[in]一个值，则该值`true`的调用是异步的; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="6821b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6821b-112">备注</span><span class="sxs-lookup"><span data-stu-id="6821b-112">Remarks</span></span>  
 <span data-ttu-id="6821b-113">如果消息请求是异步的可以使用任何任意线程将请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="6821b-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6821b-114">要求</span><span class="sxs-lookup"><span data-stu-id="6821b-114">Requirements</span></span>  
 <span data-ttu-id="6821b-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6821b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6821b-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6821b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6821b-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6821b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6821b-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6821b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6821b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6821b-119">See also</span></span>
- [<span data-ttu-id="6821b-120">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6821b-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
