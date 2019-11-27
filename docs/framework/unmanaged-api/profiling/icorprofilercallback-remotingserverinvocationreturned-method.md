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
ms.openlocfilehash: c121e403d116581ce3fa823d5d8cadbb2a58e296
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445781"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="61fbd-102">ICorProfilerCallback::RemotingServerInvocationReturned 方法</span><span class="sxs-lookup"><span data-stu-id="61fbd-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="61fbd-103">通知探查器进程已完成调用方法以响应远程方法调用请求。</span><span class="sxs-lookup"><span data-stu-id="61fbd-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61fbd-104">语法</span><span class="sxs-lookup"><span data-stu-id="61fbd-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="61fbd-105">要求</span><span class="sxs-lookup"><span data-stu-id="61fbd-105">Requirements</span></span>  
 <span data-ttu-id="61fbd-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61fbd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61fbd-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61fbd-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61fbd-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61fbd-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61fbd-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61fbd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61fbd-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61fbd-110">See also</span></span>

- [<span data-ttu-id="61fbd-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="61fbd-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
