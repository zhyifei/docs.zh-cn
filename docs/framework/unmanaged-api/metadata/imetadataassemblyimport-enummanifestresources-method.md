---
title: "IMetaDataAssemblyImport::EnumManifestResources 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumManifestResources
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa31441d060744bb17fc26a61daa7e655aa378fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="ddb12-102">IMetaDataAssemblyImport::EnumManifestResources 方法</span><span class="sxs-lookup"><span data-stu-id="ddb12-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="ddb12-103">获取一个指向为枚举器的当前程序集清单中所引用的资源。</span><span class="sxs-lookup"><span data-stu-id="ddb12-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb12-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddb12-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddb12-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddb12-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ddb12-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="ddb12-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ddb12-107">这必须是一个为 null 的值时`EnumManifestResources`首次调用方法。</span><span class="sxs-lookup"><span data-stu-id="ddb12-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="ddb12-108">[out]用于存储数组`mdManifestResource`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ddb12-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ddb12-109">[in]最大数`mdManifestResource`可以放置在令牌`rManifestResources`。</span><span class="sxs-lookup"><span data-stu-id="ddb12-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ddb12-110">[out]数`mdManifestResource`令牌实际放入`rManifestResources`。</span><span class="sxs-lookup"><span data-stu-id="ddb12-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddb12-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ddb12-111">Return Value</span></span>  
  
|<span data-ttu-id="ddb12-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddb12-112">HRESULT</span></span>|<span data-ttu-id="ddb12-113">描述</span><span class="sxs-lookup"><span data-stu-id="ddb12-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ddb12-114">`EnumManifestResources`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddb12-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ddb12-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="ddb12-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ddb12-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="ddb12-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddb12-117">惠?</span><span class="sxs-lookup"><span data-stu-id="ddb12-117">Requirements</span></span>  
 <span data-ttu-id="ddb12-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb12-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddb12-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ddb12-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddb12-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ddb12-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ddb12-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddb12-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb12-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb12-122">See Also</span></span>  
 [<span data-ttu-id="ddb12-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="ddb12-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
