---
title: "IMetaDataImport2::EnumGenericParamConstraints 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumGenericParamConstraints
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9afbcae016ce111456588ddbbc9f664dd7e76196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="9d654-102">IMetaDataImport2::EnumGenericParamConstraints 方法</span><span class="sxs-lookup"><span data-stu-id="9d654-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="9d654-103">获取与指定标记所表示的泛型参数相关联的泛型参数约束的数组的枚举数。</span><span class="sxs-lookup"><span data-stu-id="9d654-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d654-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d654-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d654-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d654-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9d654-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="9d654-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="9d654-107">[in]  一个表示其约束是要枚举的泛型参数的令牌。</span><span class="sxs-lookup"><span data-stu-id="9d654-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="9d654-108">[out]若要枚举的泛型参数约束的数组。</span><span class="sxs-lookup"><span data-stu-id="9d654-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9d654-109">[in]  请求的令牌中放置的最大数`rGenericParamConstraints`。</span><span class="sxs-lookup"><span data-stu-id="9d654-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="9d654-110">[out]指向的令牌的数目的指针置于`rGenericParamConstraints`。</span><span class="sxs-lookup"><span data-stu-id="9d654-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d654-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9d654-111">Return Value</span></span>  
  
|<span data-ttu-id="9d654-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d654-112">HRESULT</span></span>|<span data-ttu-id="9d654-113">描述</span><span class="sxs-lookup"><span data-stu-id="9d654-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9d654-114">`EnumGenericParameterConstraints`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9d654-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9d654-115">`phEnum`不包含任何成员元素。</span><span class="sxs-lookup"><span data-stu-id="9d654-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="9d654-116">在这种情况下，`pcGenericParameterConstraints`设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="9d654-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d654-117">要求</span><span class="sxs-lookup"><span data-stu-id="9d654-117">Requirements</span></span>  
 <span data-ttu-id="9d654-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d654-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d654-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d654-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d654-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9d654-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d654-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d654-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d654-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d654-122">See Also</span></span>  
 [<span data-ttu-id="9d654-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="9d654-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="9d654-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="9d654-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
