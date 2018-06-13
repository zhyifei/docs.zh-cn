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
ms.openlocfilehash: b3f32b9ab9b4e29dd101729dc43cde03985f5994
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451219"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="0ef17-102">ICorProfilerCallback::RemotingServerInvocationReturned 方法</span><span class="sxs-lookup"><span data-stu-id="0ef17-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="0ef17-103">通知探查器，在过程完成后调用的远程方法调用请求响应中的方法。</span><span class="sxs-lookup"><span data-stu-id="0ef17-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef17-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ef17-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0ef17-105">要求</span><span class="sxs-lookup"><span data-stu-id="0ef17-105">Requirements</span></span>  
 <span data-ttu-id="0ef17-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef17-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ef17-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ef17-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ef17-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ef17-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ef17-109">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ef17-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef17-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ef17-110">See Also</span></span>  
 [<span data-ttu-id="0ef17-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0ef17-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
