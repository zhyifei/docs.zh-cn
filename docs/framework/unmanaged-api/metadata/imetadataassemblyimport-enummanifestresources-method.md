---
title: IMetaDataAssemblyImport::EnumManifestResources 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cffafe9c8eac03d31c2b0b45dd65ed2c5b28861
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722630"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="a2512-102">IMetaDataAssemblyImport::EnumManifestResources 方法</span><span class="sxs-lookup"><span data-stu-id="a2512-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="a2512-103">获取一个指向枚举数的当前程序集清单中引用的资源。</span><span class="sxs-lookup"><span data-stu-id="a2512-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2512-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2512-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2512-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2512-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a2512-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="a2512-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a2512-107">这必须是一个 null 值时`EnumManifestResources`第一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="a2512-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="a2512-108">[out]用于存储数组`mdManifestResource`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="a2512-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a2512-109">[in]最大数目`mdManifestResource`令牌可以置于`rManifestResources`。</span><span class="sxs-lookup"><span data-stu-id="a2512-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a2512-110">[out]数`mdManifestResource`令牌实际置于`rManifestResources`。</span><span class="sxs-lookup"><span data-stu-id="a2512-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2512-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a2512-111">Return Value</span></span>  
  
|<span data-ttu-id="a2512-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2512-112">HRESULT</span></span>|<span data-ttu-id="a2512-113">描述</span><span class="sxs-lookup"><span data-stu-id="a2512-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a2512-114">`EnumManifestResources` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a2512-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a2512-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="a2512-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a2512-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="a2512-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2512-117">要求</span><span class="sxs-lookup"><span data-stu-id="a2512-117">Requirements</span></span>  
 <span data-ttu-id="a2512-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2512-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2512-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2512-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2512-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a2512-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2512-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2512-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2512-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2512-122">See also</span></span>
- [<span data-ttu-id="a2512-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="a2512-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
