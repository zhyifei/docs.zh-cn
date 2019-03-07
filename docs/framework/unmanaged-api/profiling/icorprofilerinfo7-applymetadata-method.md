---
title: ICorProfilerInfo7::ApplyMetaData 方法
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7fa8e2f06faa399734c44b1a52b41246296ef3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498908"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="46097-102">ICorProfilerInfo7::ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="46097-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="46097-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="46097-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="46097-104">应用新定义的元数据`IMetadataEmit::Define*`方法添加到指定的模块。</span><span class="sxs-lookup"><span data-stu-id="46097-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46097-105">语法</span><span class="sxs-lookup"><span data-stu-id="46097-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46097-106">参数</span><span class="sxs-lookup"><span data-stu-id="46097-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="46097-107">[in]已更改其元数据的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="46097-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46097-108">备注</span><span class="sxs-lookup"><span data-stu-id="46097-108">Remarks</span></span>  
 <span data-ttu-id="46097-109">如果元数据更改后[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调，您必须使用新的元数据之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="46097-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="46097-110">`ApplyMetaData` 仅支持添加以下类型的元数据：</span><span class="sxs-lookup"><span data-stu-id="46097-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="46097-111">`AssemblyRef` 通过调用创建的记录[imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)。</span><span class="sxs-lookup"><span data-stu-id="46097-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="46097-112">方法。</span><span class="sxs-lookup"><span data-stu-id="46097-112">method.</span></span>  
  
-   <span data-ttu-id="46097-113">`TypeRef` 通过调用创建的记录[imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="46097-114">`TypeSpec` 通过调用创建的记录[imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="46097-115">`MemberRef` 通过调用创建的记录[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="46097-116">`MemberSpec` 通过调用创建的记录[IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="46097-117">`UserString` 通过调用创建的记录[imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="46097-118">从.NET Core 3.0`ApplyMetaData`还支持以下类型：</span><span class="sxs-lookup"><span data-stu-id="46097-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="46097-119">`TypeDef` 通过调用创建的记录[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="46097-120">`MethodDef` 通过调用创建的记录[imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46097-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="46097-121">但是，不支持将虚拟方法添加到现有的类型。</span><span class="sxs-lookup"><span data-stu-id="46097-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="46097-122">虚拟方法必须添加之前[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="46097-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="46097-123">要求</span><span class="sxs-lookup"><span data-stu-id="46097-123">Requirements</span></span>  
 <span data-ttu-id="46097-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46097-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46097-125">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46097-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46097-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46097-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46097-127">**.NET Framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46097-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46097-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="46097-128">See also</span></span>
- [<span data-ttu-id="46097-129">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="46097-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
