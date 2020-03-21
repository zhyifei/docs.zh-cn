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
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175429"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="c93cd-102">IMetaDataImport::EnumTypeRefs 方法</span><span class="sxs-lookup"><span data-stu-id="c93cd-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="c93cd-103">枚举当前元数据范围内定义的 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="c93cd-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c93cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="c93cd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c93cd-105">parameters</span><span class="sxs-lookup"><span data-stu-id="c93cd-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c93cd-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="c93cd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c93cd-107">对于此方法的第一次调用，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c93cd-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="c93cd-108">[出]用于存储 TypeRef 令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="c93cd-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c93cd-109">[in] `rTypeRefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c93cd-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="c93cd-110">[出]指向 在 中`rTypeRefs`返回的 TypeRef 令牌数的指针。</span><span class="sxs-lookup"><span data-stu-id="c93cd-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c93cd-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c93cd-111">Return Value</span></span>  
  
|<span data-ttu-id="c93cd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c93cd-112">HRESULT</span></span>|<span data-ttu-id="c93cd-113">说明</span><span class="sxs-lookup"><span data-stu-id="c93cd-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c93cd-114">`EnumTypeRefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c93cd-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c93cd-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="c93cd-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c93cd-116">在这种情况下，`pcTypeRefs`为零。</span><span class="sxs-lookup"><span data-stu-id="c93cd-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c93cd-117">备注</span><span class="sxs-lookup"><span data-stu-id="c93cd-117">Remarks</span></span>  
 <span data-ttu-id="c93cd-118">TypeRef 令牌表示对类型的引用。</span><span class="sxs-lookup"><span data-stu-id="c93cd-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c93cd-119">要求</span><span class="sxs-lookup"><span data-stu-id="c93cd-119">Requirements</span></span>  
 <span data-ttu-id="c93cd-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c93cd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c93cd-121">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="c93cd-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c93cd-122">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="c93cd-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c93cd-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c93cd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93cd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c93cd-124">See also</span></span>

- [<span data-ttu-id="c93cd-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c93cd-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c93cd-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c93cd-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
