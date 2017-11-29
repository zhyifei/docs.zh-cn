---
title: "ICorProfilerCallback::RemotingClientReceivingReply 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f1dd027dc113abfceeb88abbc82c69ed395584e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="12b4b-102">ICorProfilerCallback::RemotingClientReceivingReply 方法</span><span class="sxs-lookup"><span data-stu-id="12b4b-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="12b4b-103">通知探查器的远程处理调用的服务器端部分已完成，并且客户端正在接收并即将处理回复。</span><span class="sxs-lookup"><span data-stu-id="12b4b-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="12b4b-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="12b4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="12b4b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="12b4b-106">[in]中提供的值与一个值，将对应[icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="12b4b-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="12b4b-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="12b4b-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="12b4b-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="12b4b-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="12b4b-109">GUID cookie 上处于活动状态的服务器端过程。</span><span class="sxs-lookup"><span data-stu-id="12b4b-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="12b4b-110">这允许轻松配对的远程处理调用。</span><span class="sxs-lookup"><span data-stu-id="12b4b-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="12b4b-111">[in]一个值，是`true`如果调用的是异步的; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="12b4b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12b4b-112">要求</span><span class="sxs-lookup"><span data-stu-id="12b4b-112">Requirements</span></span>  
 <span data-ttu-id="12b4b-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12b4b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b4b-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12b4b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12b4b-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12b4b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12b4b-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12b4b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b4b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12b4b-117">See Also</span></span>  
 [<span data-ttu-id="12b4b-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="12b4b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
