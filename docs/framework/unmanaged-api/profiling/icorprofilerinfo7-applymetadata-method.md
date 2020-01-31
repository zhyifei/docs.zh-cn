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
ms.openlocfilehash: b9e488a512ad506a8975bfff44ae02cd84c29f74
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861692"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="da117-102">ICorProfilerInfo7：： ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="da117-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="da117-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="da117-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="da117-104">将 `IMetadataEmit::Define*` 方法新定义的元数据应用于指定的模块。</span><span class="sxs-lookup"><span data-stu-id="da117-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da117-105">语法</span><span class="sxs-lookup"><span data-stu-id="da117-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da117-106">参数</span><span class="sxs-lookup"><span data-stu-id="da117-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="da117-107">中已更改其元数据的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="da117-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da117-108">备注</span><span class="sxs-lookup"><span data-stu-id="da117-108">Remarks</span></span>  
 <span data-ttu-id="da117-109">如果在[ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调之后进行元数据更改，则必须在使用新元数据之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="da117-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="da117-110">`ApplyMetaData` 仅支持添加以下类型的元数据：</span><span class="sxs-lookup"><span data-stu-id="da117-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="da117-111">`AssemblyRef` 记录，可通过调用[IMetaDataAssemblyEmit：:D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)创建。</span><span class="sxs-lookup"><span data-stu-id="da117-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="da117-112">方法中的 URL。</span><span class="sxs-lookup"><span data-stu-id="da117-112">method.</span></span>  
  
- <span data-ttu-id="da117-113">`TypeRef` 记录，可通过调用[IMetaDataEmit：:D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="da117-114">`TypeSpec` 记录，可以通过调用[IMetaDataEmit：： GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="da117-115">`MemberRef` 记录，可通过调用[IMetaDataEmit：:D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="da117-116">`MemberSpec` 记录，可通过调用[IMetaDataEmit2：:D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="da117-117">`UserString` 记录，可通过调用[IMetaDataEmit：:D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="da117-118">从 .NET Core 3.0 开始，`ApplyMetaData` 还支持以下类型：</span><span class="sxs-lookup"><span data-stu-id="da117-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="da117-119">`TypeDef` 记录，可通过调用[IMetaDataEmit：:D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="da117-120">`MethodDef` 记录，可通过调用[IMetaDataEmit：:D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="da117-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="da117-121">但是，不支持向现有类型添加虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="da117-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="da117-122">必须在[ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调之前添加虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="da117-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="da117-123">需求</span><span class="sxs-lookup"><span data-stu-id="da117-123">Requirements</span></span>  
 <span data-ttu-id="da117-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="da117-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da117-125">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da117-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da117-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da117-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da117-127">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da117-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da117-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da117-128">See also</span></span>

- [<span data-ttu-id="da117-129">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="da117-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
