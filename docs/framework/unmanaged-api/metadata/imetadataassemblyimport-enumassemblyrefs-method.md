---
title: "IMetaDataAssemblyImport::EnumAssemblyRefs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumAssemblyRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 24a289ed42a99cd26c7829d9a5789ac3027026c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="c9456-102">IMetaDataAssemblyImport::EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="c9456-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="c9456-103">枚举`mdAssemblyRef`程序集清单中定义的实例。</span><span class="sxs-lookup"><span data-stu-id="c9456-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9456-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9456-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9456-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9456-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c9456-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="c9456-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c9456-107">这必须是一个为 null 的值时`EnumAssemblyRefs`首次调用方法。</span><span class="sxs-lookup"><span data-stu-id="c9456-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="c9456-108">[out]枚举`mdAssemblyRef`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c9456-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c9456-109">[in]可以放置在的令牌的最大数目`rAssemblyRefs`数组。</span><span class="sxs-lookup"><span data-stu-id="c9456-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c9456-110">[out]中实际放置的标记数`rAssemblyRefs`。</span><span class="sxs-lookup"><span data-stu-id="c9456-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9456-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c9456-111">Return Value</span></span>  
  
|<span data-ttu-id="c9456-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9456-112">HRESULT</span></span>|<span data-ttu-id="c9456-113">描述</span><span class="sxs-lookup"><span data-stu-id="c9456-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c9456-114">`EnumAssemblyRefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c9456-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c9456-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="c9456-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c9456-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="c9456-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9456-117">要求</span><span class="sxs-lookup"><span data-stu-id="c9456-117">Requirements</span></span>  
 <span data-ttu-id="c9456-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9456-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9456-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c9456-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9456-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c9456-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9456-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9456-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9456-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9456-122">See Also</span></span>  
 [<span data-ttu-id="c9456-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="c9456-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
