---
title: IMetaDataImport::EnumProperties 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad29204e445bc61b6dc9753d594f0e4bf62930fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448568"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="aa0b3-102">IMetaDataImport::EnumProperties 方法</span><span class="sxs-lookup"><span data-stu-id="aa0b3-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="aa0b3-103">枚举 PropertyDef 标记，这些标记表示指定的 TypeDef 标记所引用的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa0b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa0b3-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa0b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="aa0b3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="aa0b3-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="aa0b3-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="aa0b3-108">[in]表示属性与要枚举的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="aa0b3-109">[out]用于存储 PropertyDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="aa0b3-110">[in] `rProperties` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="aa0b3-111">[out]PropertyDef 标记中返回的数目`rProperties`。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa0b3-112">返回值</span><span class="sxs-lookup"><span data-stu-id="aa0b3-112">Return Value</span></span>  
  
|<span data-ttu-id="aa0b3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa0b3-113">HRESULT</span></span>|<span data-ttu-id="aa0b3-114">描述</span><span class="sxs-lookup"><span data-stu-id="aa0b3-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="aa0b3-115">`EnumProperties` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="aa0b3-116">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="aa0b3-117">在这种情况下，`pcProperties`为零。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa0b3-118">要求</span><span class="sxs-lookup"><span data-stu-id="aa0b3-118">Requirements</span></span>  
 <span data-ttu-id="aa0b3-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0b3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa0b3-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa0b3-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa0b3-121">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="aa0b3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa0b3-122">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa0b3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0b3-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa0b3-123">See Also</span></span>  
 [<span data-ttu-id="aa0b3-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="aa0b3-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="aa0b3-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="aa0b3-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
