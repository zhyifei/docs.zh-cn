---
title: "IMetaDataAssemblyImport::GetExportedTypeProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetExportedTypeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e142d0c77493ac1e9ab2bf485d8e111af4fb3ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="3732c-102">IMetaDataAssemblyImport::GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="3732c-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="3732c-103">获取具有指定的元数据签名的导出类型的属性集。</span><span class="sxs-lookup"><span data-stu-id="3732c-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3732c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3732c-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3732c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3732c-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="3732c-106">[in]`mdExportedType`表示导出的类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3732c-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="3732c-107">[out]导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3732c-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3732c-108">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="3732c-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3732c-109">[out]中实际返回的宽字符数`szName`</span><span class="sxs-lookup"><span data-stu-id="3732c-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="3732c-110">[out]`mdFile`， `mdAssemblyRef`，或`mdExportedType`包含或允许访问导出的类型的属性的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3732c-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="3732c-111">[out]指向的指针`mdTypeDef`表示文件中的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="3732c-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="3732c-112">[out]指向描述应用于导出的类型的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="3732c-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="3732c-113">标志值可以是一个或多个[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="3732c-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3732c-114">要求</span><span class="sxs-lookup"><span data-stu-id="3732c-114">Requirements</span></span>  
 <span data-ttu-id="3732c-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3732c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3732c-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3732c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3732c-117">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3732c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3732c-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3732c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3732c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3732c-119">See Also</span></span>  
 [<span data-ttu-id="3732c-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="3732c-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
