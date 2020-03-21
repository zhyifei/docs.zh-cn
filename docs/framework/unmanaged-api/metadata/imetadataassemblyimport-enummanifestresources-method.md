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
ms.openlocfilehash: 22141cf46a965c0624c076bd1d86d2624e5a09f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176014"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="7f02a-102">IMetaDataAssemblyImport::EnumManifestResources 方法</span><span class="sxs-lookup"><span data-stu-id="7f02a-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="7f02a-103">获取当前程序集清单中引用的资源的指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="7f02a-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f02a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f02a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="7f02a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="7f02a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7f02a-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="7f02a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7f02a-107">当首次调用该方法时，`EnumManifestResources`这必须是 null 值。</span><span class="sxs-lookup"><span data-stu-id="7f02a-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="7f02a-108">[出]用于存储元数据令牌的`mdManifestResource`数组。</span><span class="sxs-lookup"><span data-stu-id="7f02a-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7f02a-109">[在]可放置在 中`mdManifestResource`的最大令牌数`rManifestResources`。</span><span class="sxs-lookup"><span data-stu-id="7f02a-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7f02a-110">[出]实际放置在`mdManifestResource`中的`rManifestResources`令牌数。</span><span class="sxs-lookup"><span data-stu-id="7f02a-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f02a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7f02a-111">Return Value</span></span>  
  
|<span data-ttu-id="7f02a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f02a-112">HRESULT</span></span>|<span data-ttu-id="7f02a-113">说明</span><span class="sxs-lookup"><span data-stu-id="7f02a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7f02a-114">`EnumManifestResources`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7f02a-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7f02a-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="7f02a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7f02a-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="7f02a-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f02a-117">要求</span><span class="sxs-lookup"><span data-stu-id="7f02a-117">Requirements</span></span>  
 <span data-ttu-id="7f02a-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f02a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f02a-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="7f02a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f02a-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7f02a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f02a-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f02a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f02a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f02a-122">See also</span></span>

- [<span data-ttu-id="7f02a-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="7f02a-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
