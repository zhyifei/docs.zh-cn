---
title: IMetaDataAssemblyImport::GetManifestResourceProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba99d84686974b425bcdee0bbf4770e4843e1351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992571"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="6d389-102">IMetaDataAssemblyImport::GetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="6d389-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="6d389-103">获取具有指定的元数据签名的清单资源的属性集。</span><span class="sxs-lookup"><span data-stu-id="6d389-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d389-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d389-104">Syntax</span></span>  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d389-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d389-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="6d389-106">[in]`mdManifestResource`表示要为其获取属性的资源的令牌。</span><span class="sxs-lookup"><span data-stu-id="6d389-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="6d389-107">[out]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="6d389-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6d389-108">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="6d389-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="6d389-109">[out]指向的宽字符中实际返回数的`szName`。</span><span class="sxs-lookup"><span data-stu-id="6d389-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="6d389-110">[out]一个指向`mdFile`令牌或`mdAssemblyRef`分别表示文件或程序集，包含该资源的令牌。</span><span class="sxs-lookup"><span data-stu-id="6d389-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="6d389-111">[out]指向一个值，指定到文件中资源的开头的偏移量的指针。</span><span class="sxs-lookup"><span data-stu-id="6d389-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="6d389-112">[out]指向描述应用到资源的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="6d389-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="6d389-113">标志值是一个或多个组合[CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="6d389-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d389-114">要求</span><span class="sxs-lookup"><span data-stu-id="6d389-114">Requirements</span></span>  
 <span data-ttu-id="6d389-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d389-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d389-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d389-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d389-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d389-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d389-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d389-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d389-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d389-119">See also</span></span>

- [<span data-ttu-id="6d389-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="6d389-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
