---
title: IMetaDataAssemblyImport::GetExportedTypeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177761"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="44f59-102">IMetaDataAssemblyImport::GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="44f59-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="44f59-103">使用指定的元数据签名获取导出类型的属性集。</span><span class="sxs-lookup"><span data-stu-id="44f59-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f59-104">语法</span><span class="sxs-lookup"><span data-stu-id="44f59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f59-105">parameters</span><span class="sxs-lookup"><span data-stu-id="44f59-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="44f59-106">[在]表示`mdExportedType`导出类型的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="44f59-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="44f59-107">[出]导出类型的名称。</span><span class="sxs-lookup"><span data-stu-id="44f59-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="44f59-108">[在]的大小（以宽字符表示`szName`）</span><span class="sxs-lookup"><span data-stu-id="44f59-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="44f59-109">[出]实际返回的宽字符数`szName`</span><span class="sxs-lookup"><span data-stu-id="44f59-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="44f59-110">[出]包含`mdFile`或`mdAssemblyRef`允许访问`mdExportedType`导出类型的属性的 元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="44f59-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="44f59-111">[出]指向表示文件中类型的`mdTypeDef`令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="44f59-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="44f59-112">[出]指向用于应用于导出类型的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="44f59-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="44f59-113">标志值可以是一个或多个[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="44f59-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f59-114">要求</span><span class="sxs-lookup"><span data-stu-id="44f59-114">Requirements</span></span>  
 <span data-ttu-id="44f59-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44f59-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f59-116">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="44f59-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44f59-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="44f59-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44f59-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f59-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f59-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44f59-119">See also</span></span>

- [<span data-ttu-id="44f59-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="44f59-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
