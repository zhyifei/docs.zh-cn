---
title: ICorProfilerAssemblyReferenceProvider 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: f5ba72dca25889fb57c0ae1bb2429e54a8cf2228
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128719"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="84ae4-102">ICorProfilerAssemblyReferenceProvider 方法</span><span class="sxs-lookup"><span data-stu-id="84ae4-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="84ae4-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="84ae4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="84ae4-104">启用探查器以通知程序集引用的公共语言运行时（CLR），探查器将在[ICorProfilerCallback：： ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调中添加这些引用。</span><span class="sxs-lookup"><span data-stu-id="84ae4-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84ae4-105">方法</span><span class="sxs-lookup"><span data-stu-id="84ae4-105">Methods</span></span>  
  
|<span data-ttu-id="84ae4-106">方法</span><span class="sxs-lookup"><span data-stu-id="84ae4-106">Method</span></span>|<span data-ttu-id="84ae4-107">描述</span><span class="sxs-lookup"><span data-stu-id="84ae4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84ae4-108">AddAssemblyReference 方法</span><span class="sxs-lookup"><span data-stu-id="84ae4-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="84ae4-109">向 CLR 通知探查器计划在[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调中添加的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="84ae4-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84ae4-110">备注</span><span class="sxs-lookup"><span data-stu-id="84ae4-110">Remarks</span></span>  
 <span data-ttu-id="84ae4-111">CLR 将探查器 `ICorProfilerAssemblyReferenceProvider` 接口对象传递给[ICorProfilerCallback6：： GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="84ae4-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="84ae4-112">这使探查器能够通知程序集引用的 CLR，探查器计划稍后将其添加到[ICorProfilerCallback：： ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)中。</span><span class="sxs-lookup"><span data-stu-id="84ae4-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="84ae4-113">回调中。</span><span class="sxs-lookup"><span data-stu-id="84ae4-113">callback.</span></span> <span data-ttu-id="84ae4-114">这提高了 CLR 的程序集引用闭包审核器，及其用于确定是否可以共享程序集的算法的准确性。</span><span class="sxs-lookup"><span data-stu-id="84ae4-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="84ae4-115">此接口只能在将此接口对象传递给探查器的[ICorProfilerCallback6：： GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调中使用。</span><span class="sxs-lookup"><span data-stu-id="84ae4-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84ae4-116">要求</span><span class="sxs-lookup"><span data-stu-id="84ae4-116">Requirements</span></span>  
 <span data-ttu-id="84ae4-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84ae4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84ae4-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84ae4-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84ae4-119">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84ae4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ae4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="84ae4-120">See also</span></span>

- [<span data-ttu-id="84ae4-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="84ae4-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
