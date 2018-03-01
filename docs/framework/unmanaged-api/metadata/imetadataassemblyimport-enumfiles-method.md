---
title: "IMetaDataAssemblyImport::EnumFiles 方法"
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
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ce0682f6f7719c902183778578d75dd19d56867
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="d6b64-102">IMetaDataAssemblyImport::EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="d6b64-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="d6b64-103">枚举当前程序集清单中所引用的文件。</span><span class="sxs-lookup"><span data-stu-id="d6b64-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b64-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6b64-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6b64-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6b64-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d6b64-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="d6b64-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d6b64-107">这必须是首次调用此方法的 null 值。</span><span class="sxs-lookup"><span data-stu-id="d6b64-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="d6b64-108">[out]用于存储数组`mdFile`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d6b64-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d6b64-109">[in]最大数`mdFile`可以放置在令牌`rFiles`。</span><span class="sxs-lookup"><span data-stu-id="d6b64-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d6b64-110">[out]数`mdFile`令牌实际放入`rFiles`。</span><span class="sxs-lookup"><span data-stu-id="d6b64-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6b64-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d6b64-111">Return Value</span></span>  
  
|<span data-ttu-id="d6b64-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6b64-112">HRESULT</span></span>|<span data-ttu-id="d6b64-113">描述</span><span class="sxs-lookup"><span data-stu-id="d6b64-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d6b64-114">`EnumFiles`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d6b64-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d6b64-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="d6b64-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="d6b64-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="d6b64-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6b64-117">惠?</span><span class="sxs-lookup"><span data-stu-id="d6b64-117">Requirements</span></span>  
 <span data-ttu-id="d6b64-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6b64-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6b64-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d6b64-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6b64-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d6b64-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6b64-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6b64-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b64-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6b64-122">See Also</span></span>  
 [<span data-ttu-id="d6b64-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="d6b64-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
