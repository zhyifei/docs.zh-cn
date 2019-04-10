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
ms.openlocfilehash: 410fd7a702d3aa3812b4ea053c43fdaa507a474a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176028"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="6a85d-102">IMetaDataImport::EnumProperties 方法</span><span class="sxs-lookup"><span data-stu-id="6a85d-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="6a85d-103">枚举 PropertyDef 标记，这些标记表示指定的 TypeDef 标记所引用的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="6a85d-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a85d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a85d-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a85d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a85d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6a85d-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="6a85d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6a85d-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6a85d-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="6a85d-108">[in]表示属性要枚举的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="6a85d-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="6a85d-109">[out]用于存储 PropertyDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="6a85d-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6a85d-110">[in] `rProperties` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="6a85d-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="6a85d-111">[out]在中返回的 PropertyDef 标记数`rProperties`。</span><span class="sxs-lookup"><span data-stu-id="6a85d-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a85d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6a85d-112">Return Value</span></span>  
  
|<span data-ttu-id="6a85d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a85d-113">HRESULT</span></span>|<span data-ttu-id="6a85d-114">描述</span><span class="sxs-lookup"><span data-stu-id="6a85d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumProperties` <span data-ttu-id="6a85d-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6a85d-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6a85d-116">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="6a85d-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="6a85d-117">在这种情况下，`pcProperties`为零。</span><span class="sxs-lookup"><span data-stu-id="6a85d-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a85d-118">要求</span><span class="sxs-lookup"><span data-stu-id="6a85d-118">Requirements</span></span>  
 <span data-ttu-id="6a85d-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a85d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a85d-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a85d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a85d-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6a85d-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6a85d-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6a85d-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a85d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a85d-123">See also</span></span>

- [<span data-ttu-id="6a85d-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6a85d-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a85d-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6a85d-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
