---
title: "IMetaDataAssemblyImport::EnumFiles 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumFiles
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dfe8f1c9080a963458f6dc429475a1fd0407bb2e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="e8f63-102">IMetaDataAssemblyImport::EnumFiles 方法</span><span class="sxs-lookup"><span data-stu-id="e8f63-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="e8f63-103">枚举当前程序集清单中所引用的文件。</span><span class="sxs-lookup"><span data-stu-id="e8f63-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f63-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8f63-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8f63-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8f63-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e8f63-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="e8f63-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e8f63-107">这必须是首次调用此方法的 null 值。</span><span class="sxs-lookup"><span data-stu-id="e8f63-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="e8f63-108">[out]用于存储数组`mdFile`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e8f63-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e8f63-109">[in]最大数`mdFile`可以放置在令牌`rFiles`。</span><span class="sxs-lookup"><span data-stu-id="e8f63-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e8f63-110">[out]数`mdFile`令牌实际放入`rFiles`。</span><span class="sxs-lookup"><span data-stu-id="e8f63-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8f63-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e8f63-111">Return Value</span></span>  
  
|<span data-ttu-id="e8f63-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8f63-112">HRESULT</span></span>|<span data-ttu-id="e8f63-113">描述</span><span class="sxs-lookup"><span data-stu-id="e8f63-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e8f63-114">`EnumFiles`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e8f63-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e8f63-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="e8f63-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e8f63-116">在这种情况下，`pcTokens`设置为零。</span><span class="sxs-lookup"><span data-stu-id="e8f63-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8f63-117">要求</span><span class="sxs-lookup"><span data-stu-id="e8f63-117">Requirements</span></span>  
 <span data-ttu-id="e8f63-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f63-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f63-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8f63-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8f63-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e8f63-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8f63-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f63-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f63-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8f63-122">See Also</span></span>  
 [<span data-ttu-id="e8f63-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="e8f63-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
