---
title: ICorProfilerCallback5 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 114d97e02b0a6b80c46f971ed74a24dc3c397f1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072644"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="be291-102">ICorProfilerCallback5 接口</span><span class="sxs-lookup"><span data-stu-id="be291-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="be291-103">补充信息以帮助探查器结合使用时标识活动对象的完整闭包[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)或[ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)一起使用的方法[icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)并[ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="be291-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 `ICorProfilerCallback5` <span data-ttu-id="be291-104">必须实现的托管的内存探查器订阅通知与依赖句柄。</span><span class="sxs-lookup"><span data-stu-id="be291-104">must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be291-105">备注</span><span class="sxs-lookup"><span data-stu-id="be291-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be291-106">方法</span><span class="sxs-lookup"><span data-stu-id="be291-106">Methods</span></span>  
  
|<span data-ttu-id="be291-107">方法</span><span class="sxs-lookup"><span data-stu-id="be291-107">Method</span></span>|<span data-ttu-id="be291-108">描述</span><span class="sxs-lookup"><span data-stu-id="be291-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be291-109">ConditionalWeakTableElementReferences 方法</span><span class="sxs-lookup"><span data-stu-id="be291-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="be291-110">标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。</span><span class="sxs-lookup"><span data-stu-id="be291-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be291-111">要求</span><span class="sxs-lookup"><span data-stu-id="be291-111">Requirements</span></span>  
 <span data-ttu-id="be291-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be291-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be291-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be291-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="be291-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="be291-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be291-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="be291-115">See also</span></span>

- [<span data-ttu-id="be291-116">分析接口</span><span class="sxs-lookup"><span data-stu-id="be291-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="be291-117">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="be291-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
