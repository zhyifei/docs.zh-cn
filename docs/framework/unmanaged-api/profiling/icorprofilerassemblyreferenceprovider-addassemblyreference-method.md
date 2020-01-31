---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 2357e5348192db5d41adfe1176300359440aeee3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866723"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="420df-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 方法</span><span class="sxs-lookup"><span data-stu-id="420df-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="420df-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="420df-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="420df-104">通知程序集引用的公共语言运行时（CLR），探查器计划将其添加到[ICorProfilerCallback：： ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调中。</span><span class="sxs-lookup"><span data-stu-id="420df-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420df-105">语法</span><span class="sxs-lookup"><span data-stu-id="420df-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="420df-106">参数</span><span class="sxs-lookup"><span data-stu-id="420df-106">Parameters</span></span>

- `pAssemblyRefInfo`

  <span data-ttu-id="420df-107">指向[COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md)结构的指针，该结构为 CLR 提供有关在执行程序集引用闭包审核时应考虑的程序集引用的信息。</span><span class="sxs-lookup"><span data-stu-id="420df-107">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="420df-108">备注</span><span class="sxs-lookup"><span data-stu-id="420df-108">Remarks</span></span>  
 <span data-ttu-id="420df-109">探查器为其计划从[ICorProfilerCallback6：： GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)回调的 `wszAssemblyPath` 参数中指定的程序集引用的每个目标程序集调用此方法。</span><span class="sxs-lookup"><span data-stu-id="420df-109">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="420df-110">[ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)接口对象传递给探查器的[ICorProfilerCallback6：： GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)回调，以及 `wszAssemblyPath` 参数中的程序集路径和名称。</span><span class="sxs-lookup"><span data-stu-id="420df-110">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="420df-111">需求</span><span class="sxs-lookup"><span data-stu-id="420df-111">Requirements</span></span>  
 <span data-ttu-id="420df-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="420df-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420df-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="420df-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="420df-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="420df-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="420df-115">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420df-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="420df-116">See also</span></span>

- [<span data-ttu-id="420df-117">ICorProfilerAssemblyReferenceProvider 接口</span><span class="sxs-lookup"><span data-stu-id="420df-117">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="420df-118">GetAssemblyReferences 方法</span><span class="sxs-lookup"><span data-stu-id="420df-118">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="420df-119">ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="420df-119">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
