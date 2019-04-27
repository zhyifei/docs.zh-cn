---
title: ICorProfilerCallback2::GarbageCollectionFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f613842c12b50b8a58aac1b71bf2f3c53aaf961f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914480"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="0294c-102">ICorProfilerCallback2::GarbageCollectionFinished 方法</span><span class="sxs-lookup"><span data-stu-id="0294c-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="0294c-103">垃圾回收已完成并且已对它发出所有垃圾回收回调通知探查器。</span><span class="sxs-lookup"><span data-stu-id="0294c-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0294c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0294c-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0294c-105">备注</span><span class="sxs-lookup"><span data-stu-id="0294c-105">Remarks</span></span>  
 <span data-ttu-id="0294c-106">它是安全的探查器检查其最终位置中的对象时`GarbageCollectionFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="0294c-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0294c-107">要求</span><span class="sxs-lookup"><span data-stu-id="0294c-107">Requirements</span></span>  
 <span data-ttu-id="0294c-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0294c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0294c-109">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0294c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0294c-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0294c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0294c-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0294c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0294c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0294c-112">See also</span></span>

- [<span data-ttu-id="0294c-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0294c-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0294c-114">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="0294c-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
