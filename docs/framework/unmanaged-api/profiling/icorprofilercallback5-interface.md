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
ms.openlocfilehash: 7981e7d2d2a4588e56d3c30d0ede2d003fdcd32e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865020"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="10a97-102">ICorProfilerCallback5 接口</span><span class="sxs-lookup"><span data-stu-id="10a97-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="10a97-103">当与[ICorProfilerCallback：： RootReferences](icorprofilercallback-rootreferences-method.md)或[ICorProfilerCallback2：： RootReferences2](icorprofilercallback2-rootreferences2-method.md)方法一起使用来帮助探查器识别完整的实时对象闭包和[ICorProfilerCallback：： ObjectReferences](icorprofilercallback-objectreferences-method.md)和[ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="10a97-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="10a97-104">`ICorProfilerCallback5` 必须由托管的内存探查器实现，才能订阅与依赖句柄相关的通知。</span><span class="sxs-lookup"><span data-stu-id="10a97-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10a97-105">备注</span><span class="sxs-lookup"><span data-stu-id="10a97-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10a97-106">方法</span><span class="sxs-lookup"><span data-stu-id="10a97-106">Methods</span></span>  
  
|<span data-ttu-id="10a97-107">方法</span><span class="sxs-lookup"><span data-stu-id="10a97-107">Method</span></span>|<span data-ttu-id="10a97-108">描述</span><span class="sxs-lookup"><span data-stu-id="10a97-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10a97-109">ConditionalWeakTableElementReferences 方法</span><span class="sxs-lookup"><span data-stu-id="10a97-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="10a97-110">标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。</span><span class="sxs-lookup"><span data-stu-id="10a97-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10a97-111">需求</span><span class="sxs-lookup"><span data-stu-id="10a97-111">Requirements</span></span>  
 <span data-ttu-id="10a97-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10a97-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a97-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10a97-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10a97-114">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a97-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10a97-115">See also</span></span>

- [<span data-ttu-id="10a97-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="10a97-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="10a97-117">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="10a97-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
