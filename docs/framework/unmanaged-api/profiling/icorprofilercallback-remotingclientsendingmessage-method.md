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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14717b67db03b941d33b5df61c64b5df078adaa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451423"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="8c1bd-102">ICorProfilerCallback::RemotingClientSendingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="8c1bd-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="8c1bd-103">通知探查器客户端向服务器发送请求。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c1bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c1bd-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c1bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c1bd-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="8c1bd-106">[in]中提供的值相对应的值[icorprofilercallback:: Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="8c1bd-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="8c1bd-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="8c1bd-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="8c1bd-109">GUID cookie 上处于活动状态的服务器端过程。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="8c1bd-110">这样的远程处理调用和逻辑调用堆栈的创建轻松配对。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="8c1bd-111">[in]一个值，是`true`如果调用的是异步的; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c1bd-112">要求</span><span class="sxs-lookup"><span data-stu-id="8c1bd-112">Requirements</span></span>  
 <span data-ttu-id="8c1bd-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c1bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c1bd-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c1bd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c1bd-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c1bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c1bd-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c1bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c1bd-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c1bd-117">See Also</span></span>  
 [<span data-ttu-id="8c1bd-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8c1bd-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
