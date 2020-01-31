---
title: ICorProfilerInfo10 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863239"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="fc39d-102">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="fc39d-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="fc39d-103">[ICorProfilerInfo9](icorprofilerinfo9-interface.md)的子类，提供用于修改函数 IL、从运行时查询信息以及挂起和恢复运行时的方法。</span><span class="sxs-lookup"><span data-stu-id="fc39d-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="fc39d-104">方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-104">Methods</span></span>  

| <span data-ttu-id="fc39d-105">方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-105">Method</span></span>|<span data-ttu-id="fc39d-106">描述</span><span class="sxs-lookup"><span data-stu-id="fc39d-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="fc39d-107">EnumerateObjectReferences 方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="fc39d-108">给定 ObjectID、callback 和 clientData，枚举每个对象引用（如果有）。</span><span class="sxs-lookup"><span data-stu-id="fc39d-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="fc39d-109">IsFrozenObject 方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="fc39d-110">给定 ObjectID，确定对象是否位于只读段。</span><span class="sxs-lookup"><span data-stu-id="fc39d-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="fc39d-111">GetLOHObjectSizeThreshold 方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="fc39d-112">获取配置的 LOH 阈值的值。</span><span class="sxs-lookup"><span data-stu-id="fc39d-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="fc39d-113">RequestReJITWithInliners 方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="fc39d-114">ReJITs 请求的方法，以及所请求的方法的任何 inliners。</span><span class="sxs-lookup"><span data-stu-id="fc39d-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="fc39d-115">SuspendRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="fc39d-116">挂起运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="fc39d-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="fc39d-117">ResumeRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="fc39d-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="fc39d-118">恢复运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="fc39d-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="fc39d-119">需求</span><span class="sxs-lookup"><span data-stu-id="fc39d-119">Requirements</span></span>  
<span data-ttu-id="fc39d-120">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="fc39d-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="fc39d-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc39d-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="fc39d-122">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc39d-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="fc39d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc39d-123">See also</span></span>

- [<span data-ttu-id="fc39d-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="fc39d-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
