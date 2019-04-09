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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096145"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="56fd7-102">IMetaDataAssemblyImport::GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="56fd7-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="56fd7-103">获取具有指定的元数据签名的导出类型的属性集。</span><span class="sxs-lookup"><span data-stu-id="56fd7-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56fd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="56fd7-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="56fd7-105">参数</span><span class="sxs-lookup"><span data-stu-id="56fd7-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="56fd7-106">[in]`mdExportedType`表示导出的类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="56fd7-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="56fd7-107">[out]导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="56fd7-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="56fd7-108">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="56fd7-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="56fd7-109">[out]中实际返回宽字符数</span><span class="sxs-lookup"><span data-stu-id="56fd7-109">[out] The number of wide characters actually returned in</span></span> `szName`  
  
 `ptkImplementation`  
 <span data-ttu-id="56fd7-110">[out]`mdFile`， `mdAssemblyRef`，或`mdExportedType`包含或允许访问的导出的类型属性的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="56fd7-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="56fd7-111">[out]一个指向`mdTypeDef`表示该文件中的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="56fd7-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="56fd7-112">[out]指向描述应用于导出的类型的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="56fd7-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="56fd7-113">标志值可以是一个或多个[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="56fd7-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56fd7-114">要求</span><span class="sxs-lookup"><span data-stu-id="56fd7-114">Requirements</span></span>  
 <span data-ttu-id="56fd7-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56fd7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56fd7-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="56fd7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56fd7-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="56fd7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="56fd7-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="56fd7-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56fd7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="56fd7-119">See also</span></span>

- [<span data-ttu-id="56fd7-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="56fd7-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
