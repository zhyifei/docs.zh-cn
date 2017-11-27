---
title: "ICorProfilerCallback5 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a862707dc64efbf3a9b1604a0e6a4ff1be81b43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="6dd6b-102">ICorProfilerCallback5 接口</span><span class="sxs-lookup"><span data-stu-id="6dd6b-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="6dd6b-103">补充信息以帮助探查器标识活动对象的完整闭包时使用[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)或[icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)连同方法[icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)和[ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6dd6b-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="6dd6b-104">`ICorProfilerCallback5` 必须由托管的内存探查器实现，才能订阅与依赖句柄相关的通知。</span><span class="sxs-lookup"><span data-stu-id="6dd6b-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dd6b-105">备注</span><span class="sxs-lookup"><span data-stu-id="6dd6b-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dd6b-106">方法</span><span class="sxs-lookup"><span data-stu-id="6dd6b-106">Methods</span></span>  
  
|<span data-ttu-id="6dd6b-107">方法</span><span class="sxs-lookup"><span data-stu-id="6dd6b-107">Method</span></span>|<span data-ttu-id="6dd6b-108">描述</span><span class="sxs-lookup"><span data-stu-id="6dd6b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6dd6b-109">ConditionalWeakTableElementReferences 方法</span><span class="sxs-lookup"><span data-stu-id="6dd6b-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="6dd6b-110">标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。</span><span class="sxs-lookup"><span data-stu-id="6dd6b-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6dd6b-111">要求</span><span class="sxs-lookup"><span data-stu-id="6dd6b-111">Requirements</span></span>  
 <span data-ttu-id="6dd6b-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd6b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dd6b-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6dd6b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6dd6b-114">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dd6b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd6b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dd6b-115">See Also</span></span>  
 [<span data-ttu-id="6dd6b-116">分析接口</span><span class="sxs-lookup"><span data-stu-id="6dd6b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="6dd6b-117">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="6dd6b-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
