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
ms.workload: dotnet
ms.openlocfilehash: 4052bcd07ec5abd3c560569b59600123350e810c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="477f4-102">IMetaDataImport::EnumMethods 方法</span><span class="sxs-lookup"><span data-stu-id="477f4-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="477f4-103">枚举表示指定类型的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="477f4-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="477f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="477f4-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="477f4-105">参数</span><span class="sxs-lookup"><span data-stu-id="477f4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="477f4-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="477f4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="477f4-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="477f4-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="477f4-108">[in]使用方法来枚举表示类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="477f4-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="477f4-109">[out]要存储的 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="477f4-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="477f4-110">[in]MethodDef 的最大大小`rMethods`数组。</span><span class="sxs-lookup"><span data-stu-id="477f4-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="477f4-111">[out]在中返回的 MethodDef 标记数`rMethods`。</span><span class="sxs-lookup"><span data-stu-id="477f4-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="477f4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="477f4-112">Return Value</span></span>  
  
|<span data-ttu-id="477f4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="477f4-113">HRESULT</span></span>|<span data-ttu-id="477f4-114">描述</span><span class="sxs-lookup"><span data-stu-id="477f4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="477f4-115">`EnumMethods`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="477f4-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="477f4-116">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="477f4-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="477f4-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="477f4-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="477f4-118">惠?</span><span class="sxs-lookup"><span data-stu-id="477f4-118">Requirements</span></span>  
 <span data-ttu-id="477f4-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="477f4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="477f4-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="477f4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="477f4-121">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="477f4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="477f4-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="477f4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477f4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="477f4-123">See Also</span></span>  
 [<span data-ttu-id="477f4-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="477f4-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="477f4-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="477f4-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
