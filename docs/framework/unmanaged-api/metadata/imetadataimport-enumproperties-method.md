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
ms.openlocfilehash: 4fed7dbe4ec8343a3854d1f277e3228b14c0bf21
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450023"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="4cc66-102">IMetaDataImport::EnumProperties 方法</span><span class="sxs-lookup"><span data-stu-id="4cc66-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="4cc66-103">枚举 PropertyDef 标记，这些标记表示指定的 TypeDef 标记所引用的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="4cc66-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc66-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cc66-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc66-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cc66-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4cc66-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="4cc66-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4cc66-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="4cc66-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="4cc66-108">[in] A TypeDef token representing the type with properties to enumerate.</span><span class="sxs-lookup"><span data-stu-id="4cc66-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="4cc66-109">[out] The array used to store the PropertyDef tokens.</span><span class="sxs-lookup"><span data-stu-id="4cc66-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4cc66-110">[in] `rProperties` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4cc66-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="4cc66-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="4cc66-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cc66-112">返回值</span><span class="sxs-lookup"><span data-stu-id="4cc66-112">Return Value</span></span>  
  
|<span data-ttu-id="4cc66-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cc66-113">HRESULT</span></span>|<span data-ttu-id="4cc66-114">描述</span><span class="sxs-lookup"><span data-stu-id="4cc66-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4cc66-115">`EnumProperties` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="4cc66-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4cc66-116">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="4cc66-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="4cc66-117">In that case, `pcProperties` is zero.</span><span class="sxs-lookup"><span data-stu-id="4cc66-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cc66-118">要求</span><span class="sxs-lookup"><span data-stu-id="4cc66-118">Requirements</span></span>  
 <span data-ttu-id="4cc66-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc66-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc66-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4cc66-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4cc66-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cc66-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4cc66-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc66-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc66-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cc66-123">See also</span></span>

- [<span data-ttu-id="4cc66-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4cc66-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4cc66-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4cc66-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
