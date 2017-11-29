---
title: "ICorProfilerCallback::ThreadAssignedToOSThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadAssignedToOSThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c70de2b53fd428361d5404aa406d2b2be67d0914
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="07b70-102">ICorProfilerCallback::ThreadAssignedToOSThread 方法</span><span class="sxs-lookup"><span data-stu-id="07b70-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="07b70-103">通知探查器正在使用特定的操作系统线程实现托管的线程。</span><span class="sxs-lookup"><span data-stu-id="07b70-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07b70-104">语法</span><span class="sxs-lookup"><span data-stu-id="07b70-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07b70-105">参数</span><span class="sxs-lookup"><span data-stu-id="07b70-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="07b70-106">[in]托管线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="07b70-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="07b70-107">[in]操作系统线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="07b70-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07b70-108">备注</span><span class="sxs-lookup"><span data-stu-id="07b70-108">Remarks</span></span>  
 <span data-ttu-id="07b70-109">`ThreadAssignedToOSThread`回调存在以使探查器可以保持准确映射到托管线程的操作系统线程的纤程。</span><span class="sxs-lookup"><span data-stu-id="07b70-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07b70-110">要求</span><span class="sxs-lookup"><span data-stu-id="07b70-110">Requirements</span></span>  
 <span data-ttu-id="07b70-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07b70-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07b70-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07b70-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07b70-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07b70-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07b70-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07b70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b70-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07b70-115">See Also</span></span>  
 [<span data-ttu-id="07b70-116">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="07b70-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
