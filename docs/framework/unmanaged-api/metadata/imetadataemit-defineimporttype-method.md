---
title: IMetaDataEmit::DefineImportType 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68e6f7599db55ed9429f159b380a8a9f8ae3f034
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447481"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="bcb31-102">IMetaDataEmit::DefineImportType 方法</span><span class="sxs-lookup"><span data-stu-id="bcb31-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="bcb31-103">创建定义出当前范围，并定义一个标记为该引用的指定类型的引用。</span><span class="sxs-lookup"><span data-stu-id="bcb31-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb31-104">语法</span><span class="sxs-lookup"><span data-stu-id="bcb31-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcb31-105">参数</span><span class="sxs-lookup"><span data-stu-id="bcb31-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="bcb31-106">[in][IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)表示从中导入的目标类型的程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="bcb31-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="bcb31-107">[in]数组包含指定的程序集哈希`pAssemImport`。</span><span class="sxs-lookup"><span data-stu-id="bcb31-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="bcb31-108">[in] `pbHashValue` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="bcb31-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="bcb31-109">[in][IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)表示从中导入的目标类型的元数据范围的接口。</span><span class="sxs-lookup"><span data-stu-id="bcb31-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="bcb31-110">[in]`mdTypeDef`指定的目标类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="bcb31-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="bcb31-111">[in][IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)表示目标类型导入的程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="bcb31-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="bcb31-112">[out]`mdTypeRef`在类型引用的当前作用域中定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="bcb31-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcb31-113">备注</span><span class="sxs-lookup"><span data-stu-id="bcb31-113">Remarks</span></span>  
 <span data-ttu-id="bcb31-114">在调用之前[imetadataemit:: Defineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)方法，你可以使用`DefineImportType`方法创建的类型引用，在当前范围内，为成员的父类或父接口。</span><span class="sxs-lookup"><span data-stu-id="bcb31-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb31-115">要求</span><span class="sxs-lookup"><span data-stu-id="bcb31-115">Requirements</span></span>  
 <span data-ttu-id="bcb31-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcb31-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcb31-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bcb31-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bcb31-118">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bcb31-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcb31-119">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcb31-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb31-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcb31-120">See Also</span></span>  
 [<span data-ttu-id="bcb31-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="bcb31-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="bcb31-122">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="bcb31-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
