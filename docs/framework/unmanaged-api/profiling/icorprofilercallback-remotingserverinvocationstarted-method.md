---
title: ICorProfilerCallback::RemotingServerInvocationStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83c9a4aa165057f1345de2c6f5bda80e4317d06c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221803"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="e3819-102">ICorProfilerCallback::RemotingServerInvocationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="e3819-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="e3819-103">通知探查器进程正在调用远程方法调用请求响应中的方法。</span><span class="sxs-lookup"><span data-stu-id="e3819-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3819-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3819-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="e3819-105">要求</span><span class="sxs-lookup"><span data-stu-id="e3819-105">Requirements</span></span>  
 <span data-ttu-id="e3819-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3819-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3819-107">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3819-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3819-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3819-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e3819-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e3819-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3819-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3819-110">See also</span></span>

- [<span data-ttu-id="e3819-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e3819-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
