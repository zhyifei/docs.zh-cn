---
title: "IMetaDataAssemblyImport::EnumAssemblyRefs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18dda94ac9a19a7cabbaa2a9c4cc83badb079f92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="5b70f-102">IMetaDataAssemblyImport::EnumAssemblyRefs 方法</span><span class="sxs-lookup"><span data-stu-id="5b70f-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="5b70f-103">枚举`mdAssemblyRef`程序集清单中定义的实例。</span><span class="sxs-lookup"><span data-stu-id="5b70f-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b70f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b70f-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b70f-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b70f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5b70f-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="5b70f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5b70f-107">这必须是一个为 null 的值时`EnumAssemblyRefs`首次调用方法。</span><span class="sxs-lookup"><span data-stu-id="5b70f-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="5b70f-108">[out]枚举`mdAssemblyRef`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5b70f-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5b70f-109">[in]可以放置在的令牌的最大数目`rAssemblyRefs`数组。</span><span class="sxs-lookup"><span data-stu-id="5b70f-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5b70f-110">[out]中实际放置的标记数`rAssemblyRefs`。</span><span class="sxs-lookup"><span data-stu-id="5b70f-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b70f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5b70f-111">Return Value</span></span>  
  
|<span data-ttu-id="5b70f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b70f-112">HRESULT</span></span>|<span data-ttu-id="5b70f-113">描述</span><span class="sxs-lookup"><span data-stu-id="5b70f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5b70f-114">`EnumAssemblyRefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5b70f-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5b70f-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="5b70f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5b70f-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="5b70f-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b70f-117">惠?</span><span class="sxs-lookup"><span data-stu-id="5b70f-117">Requirements</span></span>  
 <span data-ttu-id="5b70f-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b70f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b70f-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b70f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b70f-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5b70f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b70f-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b70f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b70f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b70f-122">See Also</span></span>  
 [<span data-ttu-id="5b70f-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="5b70f-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
