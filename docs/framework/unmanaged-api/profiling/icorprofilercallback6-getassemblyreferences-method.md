---
title: ICorProfilerCallback6::GetAssemblyReferences 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
ms.openlocfilehash: 0717ef5fdb6c0447ceeb801f239be08f8cca5988
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865046"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="0ad7f-102">ICorProfilerCallback6::GetAssemblyReferences 方法</span><span class="sxs-lookup"><span data-stu-id="0ad7f-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="0ad7f-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="0ad7f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0ad7f-104">当公共语言运行时执行程序集引用闭包审核时，通知探查器程序集正处于非常早期的加载阶段。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad7f-105">语法</span><span class="sxs-lookup"><span data-stu-id="0ad7f-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ad7f-106">参数</span><span class="sxs-lookup"><span data-stu-id="0ad7f-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="0ad7f-107">[in] 元数据将发生修改的程序集的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="0ad7f-108">中一个指针，指向用于指定要添加的程序集引用的[ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)接口的地址。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ad7f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0ad7f-109">Return Value</span></span>  
 <span data-ttu-id="0ad7f-110">将忽略此回调的返回值。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad7f-111">备注</span><span class="sxs-lookup"><span data-stu-id="0ad7f-111">Remarks</span></span>  
 <span data-ttu-id="0ad7f-112">调用[ICorProfilerCallback5：： SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)方法时，可通过设置[COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md)事件掩码标志来控制此回调。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="0ad7f-113">如果探查器注册了[ICorProfilerCallback6：： GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)回调方法，则运行时将传递要加载的程序集的路径和名称以及指向该方法的指向[ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)接口对象的指针。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="0ad7f-114">然后，探查器可以为它计划从 `GetAssemblyReferences` 回调中指定的程序集引用的每个目标程序集调用[ICorProfilerAssemblyReferenceProvider：： AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) `COR_PRF_ASSEMBLY_REFERENCE_INFO` 方法。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="0ad7f-115">仅当探查器必须修改程序集的元数据以添加程序集引用时，才使用 `GetAssemblyReferences` 回调。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="0ad7f-116">（但请注意，程序集元数据的实际修改是在[ICorProfilerCallback：： ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调方法中完成的。）探查器应实现 `GetAssemblyReferences` 回调方法，以通知公共语言运行时（CLR）加载模块时将添加程序集引用。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="0ad7f-117">这有助于确保即使探查器打算以后修改元数据程序集引用，CLR 在此早期阶段作出的程序集共享决策也会保持有效。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="0ad7f-118">这可以避免一些由于探查器元数据修改而导致 `SECURITY_E_INCOMPATIBLE_SHARE` 错误的实例。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="0ad7f-119">探查器使用此方法提供的[ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)对象将程序集引用添加到 CLR 程序集引用闭包查看器。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="0ad7f-120">应仅在此回调内使用[ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-120">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="0ad7f-121">从此回调对[ICorProfilerAssemblyReferenceProvider：： AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)方法的调用不会导致修改的元数据，而只会导致修改后的程序集引用闭包审核。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="0ad7f-122">探查器仍必须使用[IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)对象从引用程序集的[ICorProfilerCallback：： ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调中显式添加程序集引用，即使它实现 `GetAssemblyReferences` 回调也是如此。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="0ad7f-123">探查器应准备好接收对同一程序集的此回调的重复调用，并且应对每个这样的重复调用做出相同的响应（通过创建一组相同的[ICorProfilerAssemblyReferenceProvider：： AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)调用）。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad7f-124">需求</span><span class="sxs-lookup"><span data-stu-id="0ad7f-124">Requirements</span></span>  
 <span data-ttu-id="0ad7f-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ad7f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad7f-126">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ad7f-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ad7f-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad7f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad7f-128">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad7f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad7f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ad7f-129">See also</span></span>

- [<span data-ttu-id="0ad7f-130">ICorProfilerCallback6 接口</span><span class="sxs-lookup"><span data-stu-id="0ad7f-130">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="0ad7f-131">ModuleLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="0ad7f-131">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="0ad7f-132">COR_PRF_ASSEMBLY_REFERENCE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="0ad7f-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="0ad7f-133">ICorProfilerAssemblyReferenceProvider 接口</span><span class="sxs-lookup"><span data-stu-id="0ad7f-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
