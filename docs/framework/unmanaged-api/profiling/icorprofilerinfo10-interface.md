---
title: ICorProfilerInfo10 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449840"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="23823-102">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="23823-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="23823-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span><span class="sxs-lookup"><span data-stu-id="23823-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="23823-104">方法</span><span class="sxs-lookup"><span data-stu-id="23823-104">Methods</span></span>  

| <span data-ttu-id="23823-105">方法</span><span class="sxs-lookup"><span data-stu-id="23823-105">Method</span></span>|<span data-ttu-id="23823-106">描述</span><span class="sxs-lookup"><span data-stu-id="23823-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="23823-107">EnumerateObjectReferences Method</span><span class="sxs-lookup"><span data-stu-id="23823-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="23823-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span><span class="sxs-lookup"><span data-stu-id="23823-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="23823-109">IsFrozenObject Method</span><span class="sxs-lookup"><span data-stu-id="23823-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="23823-110">Given an ObjectID, determines whether the object is in a read-only segment.</span><span class="sxs-lookup"><span data-stu-id="23823-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="23823-111">GetLOHObjectSizeThreshold Method</span><span class="sxs-lookup"><span data-stu-id="23823-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="23823-112">Gets the value of the configured LOH threshold.</span><span class="sxs-lookup"><span data-stu-id="23823-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="23823-113">RequestReJITWithInliners Method</span><span class="sxs-lookup"><span data-stu-id="23823-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="23823-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span><span class="sxs-lookup"><span data-stu-id="23823-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="23823-115">SuspendRuntime Method</span><span class="sxs-lookup"><span data-stu-id="23823-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="23823-116">Suspends the runtime without performing a GC.</span><span class="sxs-lookup"><span data-stu-id="23823-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="23823-117">ResumeRuntime Method</span><span class="sxs-lookup"><span data-stu-id="23823-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="23823-118">Resumes the runtime without performing a GC.</span><span class="sxs-lookup"><span data-stu-id="23823-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="23823-119">要求</span><span class="sxs-lookup"><span data-stu-id="23823-119">Requirements</span></span>  
<span data-ttu-id="23823-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="23823-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="23823-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23823-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="23823-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23823-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="23823-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="23823-123">See also</span></span>

- [<span data-ttu-id="23823-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="23823-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
