---
title: IMetaDataImport2::EnumGenericParamConstraints 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f66b0145dbaece7292d2ccad169a97fbb10b6d11
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186675"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="37737-102">IMetaDataImport2::EnumGenericParamConstraints 方法</span><span class="sxs-lookup"><span data-stu-id="37737-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="37737-103">获取与指定的标记表示的泛型参数相关联的泛型参数约束的数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="37737-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37737-104">语法</span><span class="sxs-lookup"><span data-stu-id="37737-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37737-105">参数</span><span class="sxs-lookup"><span data-stu-id="37737-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="37737-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="37737-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="37737-107">[in]  表示其约束是要枚举的泛型参数的标记。</span><span class="sxs-lookup"><span data-stu-id="37737-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="37737-108">[out]若要枚举的泛型参数约束的数组。</span><span class="sxs-lookup"><span data-stu-id="37737-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="37737-109">[in]  要放置在中的令牌的请求最大数目`rGenericParamConstraints`。</span><span class="sxs-lookup"><span data-stu-id="37737-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="37737-110">[out]指向标记数的指针置于`rGenericParamConstraints`。</span><span class="sxs-lookup"><span data-stu-id="37737-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37737-111">返回值</span><span class="sxs-lookup"><span data-stu-id="37737-111">Return Value</span></span>  
  
|<span data-ttu-id="37737-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37737-112">HRESULT</span></span>|<span data-ttu-id="37737-113">描述</span><span class="sxs-lookup"><span data-stu-id="37737-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="37737-114">`EnumGenericParameterConstraints` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="37737-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="37737-115">`phEnum` 不包含任何成员元素。</span><span class="sxs-lookup"><span data-stu-id="37737-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="37737-116">在这种情况下，`pcGenericParameterConstraints`设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="37737-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37737-117">要求</span><span class="sxs-lookup"><span data-stu-id="37737-117">Requirements</span></span>  
 <span data-ttu-id="37737-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37737-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37737-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37737-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37737-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="37737-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37737-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37737-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37737-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="37737-122">See also</span></span>

- [<span data-ttu-id="37737-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="37737-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="37737-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="37737-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
