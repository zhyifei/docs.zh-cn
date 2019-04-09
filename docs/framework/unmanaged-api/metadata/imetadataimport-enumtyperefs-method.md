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
ms.openlocfilehash: de0fe4a51fbb49e80377b6b434bf3b72ddb90f02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081614"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="bd65a-102">IMetaDataImport::EnumTypeRefs 方法</span><span class="sxs-lookup"><span data-stu-id="bd65a-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="bd65a-103">枚举当前元数据范围内定义的 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="bd65a-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd65a-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd65a-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd65a-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd65a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="bd65a-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="bd65a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bd65a-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bd65a-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="bd65a-108">[out]用于存储 TypeRef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="bd65a-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bd65a-109">[in] `rTypeRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="bd65a-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="bd65a-110">[out]指向 TypeRef 标记中返回数的`rTypeRefs`。</span><span class="sxs-lookup"><span data-stu-id="bd65a-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd65a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bd65a-111">Return Value</span></span>  
  
|<span data-ttu-id="bd65a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd65a-112">HRESULT</span></span>|<span data-ttu-id="bd65a-113">描述</span><span class="sxs-lookup"><span data-stu-id="bd65a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeRefs` <span data-ttu-id="bd65a-114">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="bd65a-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bd65a-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="bd65a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="bd65a-116">在这种情况下，`pcTypeRefs`为零。</span><span class="sxs-lookup"><span data-stu-id="bd65a-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd65a-117">备注</span><span class="sxs-lookup"><span data-stu-id="bd65a-117">Remarks</span></span>  
 <span data-ttu-id="bd65a-118">TypeRef 标记表示一种类型的引用。</span><span class="sxs-lookup"><span data-stu-id="bd65a-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd65a-119">要求</span><span class="sxs-lookup"><span data-stu-id="bd65a-119">Requirements</span></span>  
 <span data-ttu-id="bd65a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd65a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd65a-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd65a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd65a-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bd65a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="bd65a-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="bd65a-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd65a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd65a-124">See also</span></span>

- [<span data-ttu-id="bd65a-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="bd65a-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bd65a-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="bd65a-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
