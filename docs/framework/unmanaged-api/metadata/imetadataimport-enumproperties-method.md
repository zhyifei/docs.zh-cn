---
title: "IMetaDataImport::EnumProperties 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumProperties
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d46e18707ff6b34e32a73aed81c2b7e57f769ed6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="200aa-102">IMetaDataImport::EnumProperties 方法</span><span class="sxs-lookup"><span data-stu-id="200aa-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="200aa-103">枚举 PropertyDef 标记，这些标记表示指定的 TypeDef 标记所引用的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="200aa-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="200aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="200aa-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="200aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="200aa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="200aa-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="200aa-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="200aa-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="200aa-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="200aa-108">[in]表示属性与要枚举的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="200aa-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="200aa-109">[out]用于存储 PropertyDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="200aa-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="200aa-110">[in] `rProperties` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="200aa-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="200aa-111">[out]PropertyDef 标记中返回的数目`rProperties`。</span><span class="sxs-lookup"><span data-stu-id="200aa-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="200aa-112">返回值</span><span class="sxs-lookup"><span data-stu-id="200aa-112">Return Value</span></span>  
  
|<span data-ttu-id="200aa-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="200aa-113">HRESULT</span></span>|<span data-ttu-id="200aa-114">描述</span><span class="sxs-lookup"><span data-stu-id="200aa-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="200aa-115">`EnumProperties`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="200aa-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="200aa-116">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="200aa-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="200aa-117">在这种情况下，`pcProperties`为零。</span><span class="sxs-lookup"><span data-stu-id="200aa-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="200aa-118">要求</span><span class="sxs-lookup"><span data-stu-id="200aa-118">Requirements</span></span>  
 <span data-ttu-id="200aa-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="200aa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="200aa-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="200aa-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="200aa-121">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="200aa-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="200aa-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="200aa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200aa-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="200aa-123">See Also</span></span>  
 [<span data-ttu-id="200aa-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="200aa-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="200aa-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="200aa-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
