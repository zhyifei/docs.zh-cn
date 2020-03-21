---
title: ICorProfilerInfo10 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175065"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="e0693-102">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="e0693-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="e0693-103">[ICorProfilerInfo9](icorprofilerinfo9-interface.md)的子类，它提供修改函数 IL、查询运行时信息以及挂起和恢复运行时的方法。</span><span class="sxs-lookup"><span data-stu-id="e0693-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="e0693-104">方法</span><span class="sxs-lookup"><span data-stu-id="e0693-104">Methods</span></span>  

| <span data-ttu-id="e0693-105">方法</span><span class="sxs-lookup"><span data-stu-id="e0693-105">Method</span></span>|<span data-ttu-id="e0693-106">说明</span><span class="sxs-lookup"><span data-stu-id="e0693-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="e0693-107">EnumerateObjectReferences 方法</span><span class="sxs-lookup"><span data-stu-id="e0693-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="e0693-108">给定 ObjectID、回调和客户端数据，枚举每个对象引用（如果有）。</span><span class="sxs-lookup"><span data-stu-id="e0693-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="e0693-109">IsFrozenObject 方法</span><span class="sxs-lookup"><span data-stu-id="e0693-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="e0693-110">给定 ObjectID，确定对象是否位于只读段中。</span><span class="sxs-lookup"><span data-stu-id="e0693-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="e0693-111">GetLOHObjectSizeThreshold 方法</span><span class="sxs-lookup"><span data-stu-id="e0693-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="e0693-112">获取配置的 LOH 阈值。</span><span class="sxs-lookup"><span data-stu-id="e0693-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="e0693-113">RequestReJITWithInliners 方法</span><span class="sxs-lookup"><span data-stu-id="e0693-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="e0693-114">重新执行请求的方法，以及所请求方法的任何内衬。</span><span class="sxs-lookup"><span data-stu-id="e0693-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="e0693-115">SuspendRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e0693-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="e0693-116">在不执行 GC 的情况下挂起运行时。</span><span class="sxs-lookup"><span data-stu-id="e0693-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="e0693-117">ResumeRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e0693-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="e0693-118">在不执行 GC 的情况下恢复运行时。</span><span class="sxs-lookup"><span data-stu-id="e0693-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="e0693-119">要求</span><span class="sxs-lookup"><span data-stu-id="e0693-119">Requirements</span></span>  
<span data-ttu-id="e0693-120">**平台：** 请参阅[.NET Core 支持的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="e0693-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="e0693-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0693-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="e0693-122">**.NET 版本：**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0693-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e0693-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0693-123">See also</span></span>

- [<span data-ttu-id="e0693-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="e0693-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
