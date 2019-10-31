---
title: ICorProfilerInfo7：： ApplyMetaData 方法
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
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130349"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="6b4cd-102">ICorProfilerInfo7：： ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="6b4cd-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="6b4cd-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="6b4cd-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="6b4cd-104">将 `IMetadataEmit::Define*` 方法新定义的元数据应用于指定的模块。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4cd-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b4cd-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b4cd-106">参数</span><span class="sxs-lookup"><span data-stu-id="6b4cd-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6b4cd-107">中已更改其元数据的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b4cd-108">备注</span><span class="sxs-lookup"><span data-stu-id="6b4cd-108">Remarks</span></span>  
 <span data-ttu-id="6b4cd-109">如果在[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调之后进行元数据更改，则必须在使用新元数据之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="6b4cd-110">`ApplyMetaData` 仅支持添加以下类型的元数据：</span><span class="sxs-lookup"><span data-stu-id="6b4cd-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="6b4cd-111">`AssemblyRef` 记录，可通过调用[IMetaDataAssemblyEmit：:D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="6b4cd-112">方法。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-112">method.</span></span>  
  
- <span data-ttu-id="6b4cd-113">`TypeRef` 记录，可通过调用[IMetaDataEmit：:D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="6b4cd-114">`TypeSpec` 记录，可以通过调用[IMetaDataEmit：： GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="6b4cd-115">`MemberRef` 记录，可通过调用[IMetaDataEmit：:D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="6b4cd-116">`MemberSpec` 记录，可通过调用[IMetaDataEmit2：:D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="6b4cd-117">`UserString` 记录，可通过调用[IMetaDataEmit：:D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="6b4cd-118">从 .NET Core 3.0 开始，`ApplyMetaData` 还支持以下类型：</span><span class="sxs-lookup"><span data-stu-id="6b4cd-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="6b4cd-119">`TypeDef` 记录，可通过调用[IMetaDataEmit：:D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="6b4cd-120">`MethodDef` 记录，可通过调用[IMetaDataEmit：:D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="6b4cd-121">但是，不支持向现有类型添加虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="6b4cd-122">必须在[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调之前添加虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b4cd-123">要求</span><span class="sxs-lookup"><span data-stu-id="6b4cd-123">Requirements</span></span>  
 <span data-ttu-id="6b4cd-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4cd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b4cd-125">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b4cd-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b4cd-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b4cd-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b4cd-127">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4cd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4cd-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b4cd-128">See also</span></span>

- [<span data-ttu-id="6b4cd-129">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="6b4cd-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
