---
title: IMetaDataImport::EnumTypeRefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8a4fe2a65244156abe1bb0da4266f949ddd3df6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447066"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="7cc1b-102">IMetaDataImport::EnumTypeRefs 方法</span><span class="sxs-lookup"><span data-stu-id="7cc1b-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="7cc1b-103">枚举当前元数据范围内定义的 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7cc1b-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cc1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7cc1b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7cc1b-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7cc1b-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="7cc1b-108">[out]用于存储的 TypeRef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7cc1b-109">[in] `rTypeRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="7cc1b-110">[out]指向 TypeRef 标记中返回数的指针`rTypeRefs`。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cc1b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7cc1b-111">Return Value</span></span>  
  
|<span data-ttu-id="7cc1b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cc1b-112">HRESULT</span></span>|<span data-ttu-id="7cc1b-113">描述</span><span class="sxs-lookup"><span data-stu-id="7cc1b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7cc1b-114">`EnumTypeRefs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7cc1b-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7cc1b-116">在这种情况下，`pcTypeRefs`为零。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cc1b-117">备注</span><span class="sxs-lookup"><span data-stu-id="7cc1b-117">Remarks</span></span>  
 <span data-ttu-id="7cc1b-118">TypeRef 标记表示一种类型的引用。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc1b-119">要求</span><span class="sxs-lookup"><span data-stu-id="7cc1b-119">Requirements</span></span>  
 <span data-ttu-id="7cc1b-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc1b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc1b-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7cc1b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cc1b-122">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7cc1b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cc1b-123">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc1b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc1b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cc1b-124">See Also</span></span>  
 [<span data-ttu-id="7cc1b-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7cc1b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7cc1b-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7cc1b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
