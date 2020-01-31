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
ms.openlocfilehash: 0e8c91f65d4ebec07689a42d4517fc100fce136d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865839"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="b96aa-102">ICorProfilerCallback::ThreadAssignedToOSThread 方法</span><span class="sxs-lookup"><span data-stu-id="b96aa-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="b96aa-103">通知探查器使用特定操作系统线程实现了托管线程。</span><span class="sxs-lookup"><span data-stu-id="b96aa-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b96aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="b96aa-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b96aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="b96aa-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="b96aa-106">中托管线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="b96aa-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="b96aa-107">中操作系统线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="b96aa-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b96aa-108">备注</span><span class="sxs-lookup"><span data-stu-id="b96aa-108">Remarks</span></span>  
 <span data-ttu-id="b96aa-109">存在 `ThreadAssignedToOSThread` 回调，以便探查器能够在操作系统线程的纤程之间保持准确的映射到托管线程。</span><span class="sxs-lookup"><span data-stu-id="b96aa-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b96aa-110">需求</span><span class="sxs-lookup"><span data-stu-id="b96aa-110">Requirements</span></span>  
 <span data-ttu-id="b96aa-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b96aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b96aa-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b96aa-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b96aa-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b96aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b96aa-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b96aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96aa-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b96aa-115">See also</span></span>

- [<span data-ttu-id="b96aa-116">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b96aa-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
