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
ms.openlocfilehash: 65c18f534771407b2dcf4710e2604e0b30cbdcdb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611041"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="852ba-102">ICorProfilerAssemblyReferenceProvider 方法</span><span class="sxs-lookup"><span data-stu-id="852ba-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="852ba-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="852ba-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="852ba-104">启用探查器以通知公共语言运行时 (CLR) 探查器将在中添加的程序集引用[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="852ba-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="852ba-105">方法</span><span class="sxs-lookup"><span data-stu-id="852ba-105">Methods</span></span>  
  
|<span data-ttu-id="852ba-106">方法</span><span class="sxs-lookup"><span data-stu-id="852ba-106">Method</span></span>|<span data-ttu-id="852ba-107">描述</span><span class="sxs-lookup"><span data-stu-id="852ba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="852ba-108">AddAssemblyReference 方法</span><span class="sxs-lookup"><span data-stu-id="852ba-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="852ba-109">通知探查器打算添加在程序集引用的 CLR [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="852ba-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="852ba-110">备注</span><span class="sxs-lookup"><span data-stu-id="852ba-110">Remarks</span></span>  
 <span data-ttu-id="852ba-111">CLR 通过探查器`ICorProfilerAssemblyReferenceProvider`接口中的对象[ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="852ba-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="852ba-112">这使探查器以通知探查器打算添加在更高版本的程序集引用的 CLR [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)。</span><span class="sxs-lookup"><span data-stu-id="852ba-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="852ba-113">回调中。</span><span class="sxs-lookup"><span data-stu-id="852ba-113">callback.</span></span> <span data-ttu-id="852ba-114">这提高了 CLR 的程序集引用闭包审核器，及其用于确定是否可以共享程序集的算法的准确性。</span><span class="sxs-lookup"><span data-stu-id="852ba-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="852ba-115">仅在使用此接口[ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)将此接口对象传递给探查器回调。</span><span class="sxs-lookup"><span data-stu-id="852ba-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="852ba-116">要求</span><span class="sxs-lookup"><span data-stu-id="852ba-116">Requirements</span></span>  
 <span data-ttu-id="852ba-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="852ba-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="852ba-118">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="852ba-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="852ba-119">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="852ba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852ba-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="852ba-120">See also</span></span>
- [<span data-ttu-id="852ba-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="852ba-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
