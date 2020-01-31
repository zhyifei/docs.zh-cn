---
title: ICorProfilerCallback::RemotingClientSendingMessage 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
ms.openlocfilehash: 8ae58344a7a17637bf08b9b5179abdba7e7060d6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866021"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="5e394-102">ICorProfilerCallback::RemotingClientSendingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="5e394-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="5e394-103">通知探查器客户端正在向服务器发送请求。</span><span class="sxs-lookup"><span data-stu-id="5e394-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e394-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e394-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e394-105">参数</span><span class="sxs-lookup"><span data-stu-id="5e394-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="5e394-106">中与以下条件下的[ICorProfilerCallback：： RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md)中提供的值对应的值：</span><span class="sxs-lookup"><span data-stu-id="5e394-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="5e394-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="5e394-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="5e394-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="5e394-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="5e394-109">GUID cookie 在服务器端进程中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="5e394-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="5e394-110">这样就可以轻松地配对远程调用和逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="5e394-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="5e394-111">中如果调用是异步的，则为 `true` 的值;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="5e394-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e394-112">需求</span><span class="sxs-lookup"><span data-stu-id="5e394-112">Requirements</span></span>  
 <span data-ttu-id="5e394-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e394-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e394-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e394-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e394-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e394-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e394-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e394-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e394-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e394-117">See also</span></span>

- [<span data-ttu-id="5e394-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="5e394-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
