---
title: IMetaDataImport2::EnumGenericParams 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ecd1c714f41c76833ef6a0a4b7be87e338ca1a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448825"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="50d8a-102">IMetaDataImport2::EnumGenericParams 方法</span><span class="sxs-lookup"><span data-stu-id="50d8a-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="50d8a-103">获取与指定的 TypeDef 或 MethodDef 相关联的泛型参数标记为数组的枚举器令牌。</span><span class="sxs-lookup"><span data-stu-id="50d8a-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50d8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="50d8a-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50d8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="50d8a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="50d8a-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="50d8a-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="50d8a-107">[in]其泛型参数，则枚举 TypeDef 或 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="50d8a-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="50d8a-108">[out]若要枚举的泛型参数的数组。</span><span class="sxs-lookup"><span data-stu-id="50d8a-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="50d8a-109">[in]请求的令牌中放置的最大数`rGenericParams`。</span><span class="sxs-lookup"><span data-stu-id="50d8a-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="50d8a-110">[out]返回的标记数置于`rGenericParams`。</span><span class="sxs-lookup"><span data-stu-id="50d8a-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50d8a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="50d8a-111">Return Value</span></span>  
  
|<span data-ttu-id="50d8a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50d8a-112">HRESULT</span></span>|<span data-ttu-id="50d8a-113">描述</span><span class="sxs-lookup"><span data-stu-id="50d8a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="50d8a-114">`EnumGenericParams` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="50d8a-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="50d8a-115">`phEnum` 不包含任何成员元素。</span><span class="sxs-lookup"><span data-stu-id="50d8a-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="50d8a-116">在这种情况下，`pcGenericParams`设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="50d8a-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50d8a-117">要求</span><span class="sxs-lookup"><span data-stu-id="50d8a-117">Requirements</span></span>  
 <span data-ttu-id="50d8a-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50d8a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50d8a-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50d8a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50d8a-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="50d8a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50d8a-121">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50d8a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d8a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="50d8a-122">See Also</span></span>  
 [<span data-ttu-id="50d8a-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="50d8a-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="50d8a-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="50d8a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
