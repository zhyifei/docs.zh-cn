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
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177660"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="ac5e2-102">IMetaDataAssemblyImport::GetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="ac5e2-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="ac5e2-103">使用指定的元数据签名获取清单资源的属性集。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac5e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac5e2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ac5e2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ac5e2-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="ac5e2-106">[在]表示`mdManifestResource`要为其获取属性的资源的令牌。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="ac5e2-107">[出]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ac5e2-108">[在]大字符的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ac5e2-109">[出]指向 中实际返回的宽字符数的指针`szName`。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ac5e2-110">[出]指向分别表示包含`mdFile`资源的文件或`mdAssemblyRef`程序集的令牌或令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="ac5e2-111">[出]指向指定偏移到文件中资源开头的值的指针。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="ac5e2-112">[出]指向用于描述应用于资源的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="ac5e2-113">标志值是一个或多个[CorManifest 资源标志](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac5e2-114">要求</span><span class="sxs-lookup"><span data-stu-id="ac5e2-114">Requirements</span></span>  
 <span data-ttu-id="ac5e2-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac5e2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac5e2-116">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="ac5e2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac5e2-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ac5e2-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac5e2-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac5e2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5e2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac5e2-119">See also</span></span>

- [<span data-ttu-id="ac5e2-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="ac5e2-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
