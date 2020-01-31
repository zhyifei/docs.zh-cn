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
ms.openlocfilehash: 6e045a99de9ad30516fd12a7b490e26c860bde7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866008"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="89ead-102">ICorProfilerCallback::RemotingServerReceivingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="89ead-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="89ead-103">通知探查器进程已收到远程方法调用或激活请求。</span><span class="sxs-lookup"><span data-stu-id="89ead-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89ead-104">语法</span><span class="sxs-lookup"><span data-stu-id="89ead-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89ead-105">参数</span><span class="sxs-lookup"><span data-stu-id="89ead-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="89ead-106">中与以下条件下的[ICorProfilerCallback：： RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)中提供的值对应的值：</span><span class="sxs-lookup"><span data-stu-id="89ead-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="89ead-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="89ead-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="89ead-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="89ead-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="89ead-109">GUID cookie 在客户端进程中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="89ead-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="89ead-110">这样就可以轻松地配对远程调用和逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="89ead-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="89ead-111">中如果调用是异步的，则为 `true` 的值;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="89ead-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89ead-112">备注</span><span class="sxs-lookup"><span data-stu-id="89ead-112">Remarks</span></span>  
 <span data-ttu-id="89ead-113">如果消息请求是异步的，则该请求可由任意线程提供服务。</span><span class="sxs-lookup"><span data-stu-id="89ead-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89ead-114">需求</span><span class="sxs-lookup"><span data-stu-id="89ead-114">Requirements</span></span>  
 <span data-ttu-id="89ead-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89ead-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89ead-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89ead-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89ead-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89ead-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89ead-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89ead-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ead-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89ead-119">See also</span></span>

- [<span data-ttu-id="89ead-120">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="89ead-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
