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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186675"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="6bf7a-102">IMetaDataImport2::EnumGenericParamConstraints 方法</span><span class="sxs-lookup"><span data-stu-id="6bf7a-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="6bf7a-103">获取与指定的标记表示的泛型参数相关联的泛型参数约束的数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf7a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6bf7a-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bf7a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6bf7a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6bf7a-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="6bf7a-107">[in]  表示其约束是要枚举的泛型参数的标记。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="6bf7a-108">[out]若要枚举的泛型参数约束的数组。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6bf7a-109">[in]  要放置在中的令牌的请求最大数目`rGenericParamConstraints`。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="6bf7a-110">[out]指向标记数的指针置于`rGenericParamConstraints`。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bf7a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6bf7a-111">Return Value</span></span>  
  
|<span data-ttu-id="6bf7a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6bf7a-112">HRESULT</span></span>|<span data-ttu-id="6bf7a-113">描述</span><span class="sxs-lookup"><span data-stu-id="6bf7a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` <span data-ttu-id="6bf7a-114">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-114">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="6bf7a-115">不包含任何成员元素。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-115">has no member elements.</span></span> <span data-ttu-id="6bf7a-116">在这种情况下，`pcGenericParameterConstraints`设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bf7a-117">要求</span><span class="sxs-lookup"><span data-stu-id="6bf7a-117">Requirements</span></span>  
 <span data-ttu-id="6bf7a-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf7a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bf7a-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bf7a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bf7a-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6bf7a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6bf7a-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6bf7a-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6bf7a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf7a-122">See also</span></span>

- [<span data-ttu-id="6bf7a-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6bf7a-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="6bf7a-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6bf7a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
