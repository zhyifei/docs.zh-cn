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
ms.openlocfilehash: 04956fb5519c66141f4bd7330367f6c78b4e7bc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453953"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="e45dc-102">ICorProfilerCallback::RemotingClientReceivingReply 方法</span><span class="sxs-lookup"><span data-stu-id="e45dc-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="e45dc-103">通知探查器的远程处理调用的服务器端部分已完成，并且客户端正在接收并即将处理回复。</span><span class="sxs-lookup"><span data-stu-id="e45dc-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e45dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="e45dc-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e45dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="e45dc-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="e45dc-106">[in]中提供的值与一个值，将对应[icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)在这些情况下：</span><span class="sxs-lookup"><span data-stu-id="e45dc-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="e45dc-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="e45dc-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="e45dc-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="e45dc-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="e45dc-109">GUID cookie 上处于活动状态的服务器端过程。</span><span class="sxs-lookup"><span data-stu-id="e45dc-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="e45dc-110">这允许轻松配对的远程处理调用。</span><span class="sxs-lookup"><span data-stu-id="e45dc-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="e45dc-111">[in]一个值，是`true`如果调用的是异步的; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="e45dc-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e45dc-112">要求</span><span class="sxs-lookup"><span data-stu-id="e45dc-112">Requirements</span></span>  
 <span data-ttu-id="e45dc-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e45dc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e45dc-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e45dc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e45dc-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e45dc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e45dc-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e45dc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e45dc-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e45dc-117">See Also</span></span>  
 [<span data-ttu-id="e45dc-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e45dc-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
