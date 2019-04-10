---
title: ICorProfilerCallback::RemotingServerInvocationReturned 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00f5fd44d340a76200537871a9860f67601b66d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208704"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="baeab-102">ICorProfilerCallback::RemotingServerInvocationReturned 方法</span><span class="sxs-lookup"><span data-stu-id="baeab-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="baeab-103">通知探查器进程已完成调用远程方法调用请求响应中的方法。</span><span class="sxs-lookup"><span data-stu-id="baeab-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baeab-104">语法</span><span class="sxs-lookup"><span data-stu-id="baeab-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="baeab-105">要求</span><span class="sxs-lookup"><span data-stu-id="baeab-105">Requirements</span></span>  
 <span data-ttu-id="baeab-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="baeab-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baeab-107">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="baeab-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="baeab-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baeab-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="baeab-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="baeab-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="baeab-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="baeab-110">See also</span></span>

- [<span data-ttu-id="baeab-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="baeab-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
