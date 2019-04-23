---
title: IMetaDataEmit::DefineImportMember 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81acda4d395563fc8e0000e38036d1aaa0f14471
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222687"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="958a8-102">IMetaDataEmit::DefineImportMember 方法</span><span class="sxs-lookup"><span data-stu-id="958a8-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="958a8-103">创建对指定成员的类型或模块的当前作用域之外定义，并定义该引用的令牌的引用。</span><span class="sxs-lookup"><span data-stu-id="958a8-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="958a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="958a8-104">Syntax</span></span>  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="958a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="958a8-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="958a8-106">[in][IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)表示从中导入的目标成员的程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="958a8-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="958a8-107">[in]一个数组，包含由指定的程序集的哈希`pAssemImport`。</span><span class="sxs-lookup"><span data-stu-id="958a8-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="958a8-108">[in] `pbHashValue` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="958a8-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="958a8-109">[in][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)表示从中导入的目标成员的元数据范围的接口。</span><span class="sxs-lookup"><span data-stu-id="958a8-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="958a8-110">[in]指定目标成员的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="958a8-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="958a8-111">标记可以是`mdMethodDef`（适用于成员方法）， `mdProperty` （适用于成员属性），或`mdFieldDef`（适用于成员字段） 令牌。</span><span class="sxs-lookup"><span data-stu-id="958a8-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="958a8-112">[in][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)表示目标成员导入的程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="958a8-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="958a8-113">[in]`mdTypeRef`或`mdModuleRef`令牌类型或模块，分别，拥有的目标成员。</span><span class="sxs-lookup"><span data-stu-id="958a8-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="958a8-114">[out]`mdMemberRef`在成员引用的当前作用域中定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="958a8-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="958a8-115">备注</span><span class="sxs-lookup"><span data-stu-id="958a8-115">Remarks</span></span>  
 <span data-ttu-id="958a8-116">`DefineImportMember`方法查找由指定的成员`mbMember`，即定义另一个作用域中指定的`pImport`，并检索其属性。</span><span class="sxs-lookup"><span data-stu-id="958a8-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="958a8-117">使用此信息来调用[imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)要创建成员引用的当前作用域中的方法。</span><span class="sxs-lookup"><span data-stu-id="958a8-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="958a8-118">通常情况下，使用之前`DefineImportMember`方法，您必须创建，在当前作用域、 类型引用或目标成员的父类、 接口或模块的模块参考。</span><span class="sxs-lookup"><span data-stu-id="958a8-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="958a8-119">然后传入此引用的元数据标记`tkParent`参数。</span><span class="sxs-lookup"><span data-stu-id="958a8-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="958a8-120">不需要创建对目标成员的父级的引用，如果将在解决更高版本的编译器或链接器。</span><span class="sxs-lookup"><span data-stu-id="958a8-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="958a8-121">总结：</span><span class="sxs-lookup"><span data-stu-id="958a8-121">To summarize:</span></span>  
  
-   <span data-ttu-id="958a8-122">如果目标成员是字段或方法，可以使用两种[imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)或[imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)方法为创建的类型引用，在当前范围内，成员的父类或父接口。</span><span class="sxs-lookup"><span data-stu-id="958a8-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
-   <span data-ttu-id="958a8-123">如果目标成员的全局变量或全局函数 （即，不是成员的类或接口），请使用[imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)方法中成员的父级的当前范围，创建模块引用模块。</span><span class="sxs-lookup"><span data-stu-id="958a8-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
-   <span data-ttu-id="958a8-124">如果目标成员的父级将由编译器或链接器的更高版本解析，则传递`mdTokenNil`在`tkParent`。</span><span class="sxs-lookup"><span data-stu-id="958a8-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="958a8-125">此应用的唯一情况是全局函数或全局变量从最终将链接到当前模块的.obj 文件导入和合并的元数据。</span><span class="sxs-lookup"><span data-stu-id="958a8-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="958a8-126">要求</span><span class="sxs-lookup"><span data-stu-id="958a8-126">Requirements</span></span>  
 <span data-ttu-id="958a8-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="958a8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="958a8-128">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="958a8-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="958a8-129">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="958a8-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="958a8-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="958a8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958a8-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="958a8-131">See also</span></span>

- [<span data-ttu-id="958a8-132">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="958a8-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="958a8-133">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="958a8-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
