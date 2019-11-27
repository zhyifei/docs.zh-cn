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
ms.openlocfilehash: 5b4b0682b2bddff96cb3d720900ed3aa39f06f9d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431848"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="1d56b-102">IMetaDataEmit::DefineImportType 方法</span><span class="sxs-lookup"><span data-stu-id="1d56b-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="1d56b-103">创建对在当前范围外定义的指定类型的引用，并定义该引用的标记。</span><span class="sxs-lookup"><span data-stu-id="1d56b-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d56b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d56b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="1d56b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d56b-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="1d56b-106">中一个[IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口，它表示从其导入目标类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="1d56b-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="1d56b-107">中一个数组，包含 `pAssemImport`指定的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="1d56b-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="1d56b-108">[in] `pbHashValue` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="1d56b-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="1d56b-109">中表示要从其导入目标类型的元数据范围的[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1d56b-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="1d56b-110">中指定目标类型的 `mdTypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="1d56b-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="1d56b-111">中一个[IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)接口，该接口表示要将目标类型导入到其中的程序集。</span><span class="sxs-lookup"><span data-stu-id="1d56b-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="1d56b-112">弄在类型引用的当前范围内定义 `mdTypeRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="1d56b-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d56b-113">备注</span><span class="sxs-lookup"><span data-stu-id="1d56b-113">Remarks</span></span>  
 <span data-ttu-id="1d56b-114">在调用[IMetaDataEmit：:D efineimportmember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)方法之前，可以使用 `DefineImportType` 方法为成员的父类或父接口创建类型引用（在当前范围内）。</span><span class="sxs-lookup"><span data-stu-id="1d56b-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d56b-115">要求</span><span class="sxs-lookup"><span data-stu-id="1d56b-115">Requirements</span></span>  
 <span data-ttu-id="1d56b-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d56b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d56b-117">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1d56b-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d56b-118">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1d56b-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d56b-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d56b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d56b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d56b-120">See also</span></span>

- [<span data-ttu-id="1d56b-121">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="1d56b-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1d56b-122">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="1d56b-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
