---
title: "IMetaDataImport::EnumMethods 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d56c87d7073886d13e530501168801c6c69d9ce9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="0044f-102">IMetaDataImport::EnumMethods 方法</span><span class="sxs-lookup"><span data-stu-id="0044f-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="0044f-103">枚举表示指定类型的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="0044f-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0044f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0044f-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0044f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0044f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0044f-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="0044f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0044f-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0044f-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="0044f-108">[in]使用方法来枚举表示类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="0044f-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="0044f-109">[out]要存储的 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="0044f-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0044f-110">[in]MethodDef 的最大大小`rMethods`数组。</span><span class="sxs-lookup"><span data-stu-id="0044f-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0044f-111">[out]在中返回的 MethodDef 标记数`rMethods`。</span><span class="sxs-lookup"><span data-stu-id="0044f-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0044f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0044f-112">Return Value</span></span>  
  
|<span data-ttu-id="0044f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0044f-113">HRESULT</span></span>|<span data-ttu-id="0044f-114">描述</span><span class="sxs-lookup"><span data-stu-id="0044f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0044f-115">`EnumMethods`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0044f-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0044f-116">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="0044f-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="0044f-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="0044f-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0044f-118">要求</span><span class="sxs-lookup"><span data-stu-id="0044f-118">Requirements</span></span>  
 <span data-ttu-id="0044f-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0044f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0044f-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0044f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0044f-121">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0044f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0044f-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0044f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0044f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0044f-123">See Also</span></span>  
 [<span data-ttu-id="0044f-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="0044f-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0044f-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="0044f-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
