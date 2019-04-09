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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bad1cc71b9a27896141837a6d342f2cfe068fc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089726"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="304db-102">ICorProfilerAssemblyReferenceProvider 方法</span><span class="sxs-lookup"><span data-stu-id="304db-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="304db-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="304db-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="304db-104">启用探查器以通知公共语言运行时 (CLR) 探查器将在中添加的程序集引用[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="304db-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="304db-105">方法</span><span class="sxs-lookup"><span data-stu-id="304db-105">Methods</span></span>  
  
|<span data-ttu-id="304db-106">方法</span><span class="sxs-lookup"><span data-stu-id="304db-106">Method</span></span>|<span data-ttu-id="304db-107">描述</span><span class="sxs-lookup"><span data-stu-id="304db-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="304db-108">AddAssemblyReference 方法</span><span class="sxs-lookup"><span data-stu-id="304db-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="304db-109">通知探查器打算添加在程序集引用的 CLR [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="304db-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="304db-110">备注</span><span class="sxs-lookup"><span data-stu-id="304db-110">Remarks</span></span>  
 <span data-ttu-id="304db-111">CLR 通过探查器`ICorProfilerAssemblyReferenceProvider`接口中的对象[ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="304db-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="304db-112">这使探查器以通知探查器打算添加在更高版本的程序集引用的 CLR [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="304db-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="304db-113">回调中。</span><span class="sxs-lookup"><span data-stu-id="304db-113">callback.</span></span> <span data-ttu-id="304db-114">这提高了 CLR 的程序集引用闭包审核器，及其用于确定是否可以共享程序集的算法的准确性。</span><span class="sxs-lookup"><span data-stu-id="304db-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="304db-115">仅在使用此接口[ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)将此接口对象传递给探查器回调。</span><span class="sxs-lookup"><span data-stu-id="304db-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="304db-116">要求</span><span class="sxs-lookup"><span data-stu-id="304db-116">Requirements</span></span>  
 <span data-ttu-id="304db-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="304db-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="304db-118">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="304db-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="304db-119">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="304db-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="304db-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="304db-120">See also</span></span>

- [<span data-ttu-id="304db-121">分析接口</span><span class="sxs-lookup"><span data-stu-id="304db-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
