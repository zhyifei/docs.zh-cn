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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175858"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="edb66-102">IMetaDataEmit::DefineImportMember 方法</span><span class="sxs-lookup"><span data-stu-id="edb66-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="edb66-103">创建对在当前作用域之外定义的类型或模块的指定成员的引用，并为该引用定义令牌。</span><span class="sxs-lookup"><span data-stu-id="edb66-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb66-104">语法</span><span class="sxs-lookup"><span data-stu-id="edb66-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="edb66-105">parameters</span><span class="sxs-lookup"><span data-stu-id="edb66-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="edb66-106">[在][IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)，表示从中导入目标成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="edb66-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="edb66-107">[在]包含 的数组，其中包含 由 指定的`pAssemImport`程序集的哈希值。</span><span class="sxs-lookup"><span data-stu-id="edb66-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="edb66-108">[in] `pbHashValue` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="edb66-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="edb66-109">[在][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口，表示从中导入目标成员的元数据范围。</span><span class="sxs-lookup"><span data-stu-id="edb66-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="edb66-110">[在]指定目标成员的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="edb66-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="edb66-111">令牌可以是`mdMethodDef`（对于成员方法）、（`mdProperty`对于成员属性）或`mdFieldDef`（对于成员字段）的令牌。</span><span class="sxs-lookup"><span data-stu-id="edb66-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="edb66-112">[在][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)接口，表示将目标成员导入到的程序集。</span><span class="sxs-lookup"><span data-stu-id="edb66-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="edb66-113">[在]分别`mdTypeRef`拥有`mdModuleRef`目标成员的类型或模块的 或 令牌。</span><span class="sxs-lookup"><span data-stu-id="edb66-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="edb66-114">[出]在`mdMemberRef`成员引用的当前作用域中定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="edb66-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edb66-115">备注</span><span class="sxs-lookup"><span data-stu-id="edb66-115">Remarks</span></span>  
 <span data-ttu-id="edb66-116">方法`DefineImportMember`查找由`mbMember`指定的成员，该成员在由 指定的另一个作用域中定义`pImport`，由 指定并检索其属性。</span><span class="sxs-lookup"><span data-stu-id="edb66-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="edb66-117">它使用此信息调用当前作用域中的[IMetaDataEmit：:Define会员Ref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法来创建成员引用。</span><span class="sxs-lookup"><span data-stu-id="edb66-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="edb66-118">通常，在使用`DefineImportMember`方法之前，必须在当前作用域中为目标成员的父类、接口或模块创建类型引用或模块引用。</span><span class="sxs-lookup"><span data-stu-id="edb66-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="edb66-119">然后，在参数中传递此引用的`tkParent`元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="edb66-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="edb66-120">如果编译器或链接器稍后将解析目标成员的父项，则无需创建对目标成员的父项的引用。</span><span class="sxs-lookup"><span data-stu-id="edb66-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="edb66-121">总结：</span><span class="sxs-lookup"><span data-stu-id="edb66-121">To summarize:</span></span>  
  
- <span data-ttu-id="edb66-122">如果目标成员是字段或方法，请使用[IMetaDataEmit：:DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)或[IMetaDataEmit：:DefineImportType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)，为成员的父类或父接口在当前作用域中创建类型引用。</span><span class="sxs-lookup"><span data-stu-id="edb66-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="edb66-123">如果目标成员是全局变量或全局函数（即不是类或接口的成员），请使用[IMetaDataEmit：:DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)方法为成员的父模块在当前作用域中创建模块引用。</span><span class="sxs-lookup"><span data-stu-id="edb66-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="edb66-124">如果稍后编译器或链接器将解析目标成员的父成员的父级，则将传递`mdTokenNil``tkParent`。</span><span class="sxs-lookup"><span data-stu-id="edb66-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="edb66-125">唯一适用这种情况的情况是，全局函数或全局变量从 .obj 文件导入，该文件最终将链接到当前模块并合并元数据。</span><span class="sxs-lookup"><span data-stu-id="edb66-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edb66-126">要求</span><span class="sxs-lookup"><span data-stu-id="edb66-126">Requirements</span></span>  
 <span data-ttu-id="edb66-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edb66-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edb66-128">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="edb66-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edb66-129">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="edb66-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edb66-130">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edb66-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb66-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edb66-131">See also</span></span>

- [<span data-ttu-id="edb66-132">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="edb66-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="edb66-133">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="edb66-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
