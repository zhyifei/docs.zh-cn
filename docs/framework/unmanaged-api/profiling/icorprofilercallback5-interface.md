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
ms.openlocfilehash: ce34d43091cdee0bca88f94711e49072fa4fd08c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430062"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="8888e-102">ICorProfilerCallback5 接口</span><span class="sxs-lookup"><span data-stu-id="8888e-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="8888e-103">当与[ICorProfilerCallback：： RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)或[ICorProfilerCallback2：： RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)方法一起使用来帮助探查器识别完整的实时对象闭包和[ICorProfilerCallback：： ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)和[ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8888e-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="8888e-104">`ICorProfilerCallback5` 必须由托管内存探查器实现才能订阅与从属句柄相关的通知。</span><span class="sxs-lookup"><span data-stu-id="8888e-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8888e-105">备注</span><span class="sxs-lookup"><span data-stu-id="8888e-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8888e-106">方法</span><span class="sxs-lookup"><span data-stu-id="8888e-106">Methods</span></span>  
  
|<span data-ttu-id="8888e-107">方法</span><span class="sxs-lookup"><span data-stu-id="8888e-107">Method</span></span>|<span data-ttu-id="8888e-108">说明</span><span class="sxs-lookup"><span data-stu-id="8888e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8888e-109">ConditionalWeakTableElementReferences 方法</span><span class="sxs-lookup"><span data-stu-id="8888e-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="8888e-110">标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。</span><span class="sxs-lookup"><span data-stu-id="8888e-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8888e-111">要求</span><span class="sxs-lookup"><span data-stu-id="8888e-111">Requirements</span></span>  
 <span data-ttu-id="8888e-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8888e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8888e-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8888e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8888e-114">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8888e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8888e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8888e-115">See also</span></span>

- [<span data-ttu-id="8888e-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="8888e-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="8888e-117">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="8888e-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
