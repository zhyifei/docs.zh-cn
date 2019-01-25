---
title: ICorProfilerCallback::ThreadAssignedToOSThread 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c55c6ffea0f3688fc7c3c3283701b4e35f1fcbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651976"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="9302d-102">ICorProfilerCallback::ThreadAssignedToOSThread 方法</span><span class="sxs-lookup"><span data-stu-id="9302d-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="9302d-103">通知探查器正在使用一个特定的操作系统线程实现一个托管的线程。</span><span class="sxs-lookup"><span data-stu-id="9302d-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9302d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9302d-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9302d-105">参数</span><span class="sxs-lookup"><span data-stu-id="9302d-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="9302d-106">[in]托管线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="9302d-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="9302d-107">[in]操作系统线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="9302d-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9302d-108">备注</span><span class="sxs-lookup"><span data-stu-id="9302d-108">Remarks</span></span>  
 <span data-ttu-id="9302d-109">`ThreadAssignedToOSThread`回调存在以使探查器能够保持正确映射到托管线程的操作系统线程的纤程。</span><span class="sxs-lookup"><span data-stu-id="9302d-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9302d-110">要求</span><span class="sxs-lookup"><span data-stu-id="9302d-110">Requirements</span></span>  
 <span data-ttu-id="9302d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9302d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9302d-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9302d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9302d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9302d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9302d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9302d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9302d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9302d-115">See also</span></span>
- [<span data-ttu-id="9302d-116">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9302d-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
