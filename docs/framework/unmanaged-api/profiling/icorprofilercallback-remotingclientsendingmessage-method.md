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
ms.openlocfilehash: 61a36ff23bf9deac25983f06387b2bbbfd49546b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133180"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="9d57b-102">ICorProfilerCallback::RemotingClientSendingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="9d57b-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="9d57b-103">通知探查器客户端向服务器发送请求。</span><span class="sxs-lookup"><span data-stu-id="9d57b-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d57b-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d57b-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d57b-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d57b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="9d57b-106">[in]使用中提供的值相对应的值[icorprofilercallback:: Remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="9d57b-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="9d57b-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="9d57b-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="9d57b-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="9d57b-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="9d57b-109">GUID cookie 处于活动状态的服务器端的过程。</span><span class="sxs-lookup"><span data-stu-id="9d57b-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="9d57b-110">这允许轻松配对的远程处理调用以及逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="9d57b-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="9d57b-111">[in]一个值，则该值`true`的调用是异步的; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="9d57b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d57b-112">要求</span><span class="sxs-lookup"><span data-stu-id="9d57b-112">Requirements</span></span>  
 <span data-ttu-id="9d57b-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d57b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d57b-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d57b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d57b-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d57b-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9d57b-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="9d57b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d57b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d57b-117">See also</span></span>

- [<span data-ttu-id="9d57b-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9d57b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
