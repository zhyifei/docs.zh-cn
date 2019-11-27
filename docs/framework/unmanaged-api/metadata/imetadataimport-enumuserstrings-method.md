---
title: IMetaDataImport::EnumUserStrings 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: 1c9f15881d3515f24a63f29e9337a7a356937f2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449942"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="653ac-102">IMetaDataImport::EnumUserStrings 方法</span><span class="sxs-lookup"><span data-stu-id="653ac-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="653ac-103">枚举表示当前元数据范围内的硬编码字符串的 String 标记。</span><span class="sxs-lookup"><span data-stu-id="653ac-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="653ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="653ac-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="653ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="653ac-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="653ac-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="653ac-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="653ac-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="653ac-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="653ac-108">弄用于存储字符串标记的数组。</span><span class="sxs-lookup"><span data-stu-id="653ac-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="653ac-109">[in] `rStrings` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="653ac-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="653ac-110">弄`rStrings`中返回的字符串标记的数目。</span><span class="sxs-lookup"><span data-stu-id="653ac-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="653ac-111">返回值</span><span class="sxs-lookup"><span data-stu-id="653ac-111">Return Value</span></span>  
  
|<span data-ttu-id="653ac-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="653ac-112">HRESULT</span></span>|<span data-ttu-id="653ac-113">说明</span><span class="sxs-lookup"><span data-stu-id="653ac-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="653ac-114">`EnumUserStrings` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="653ac-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="653ac-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="653ac-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="653ac-116">在这种情况下，`pcStrings` 为零。</span><span class="sxs-lookup"><span data-stu-id="653ac-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="653ac-117">备注</span><span class="sxs-lookup"><span data-stu-id="653ac-117">Remarks</span></span>  
 <span data-ttu-id="653ac-118">字符串标记由[IMetaDataEmit：:D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法创建。</span><span class="sxs-lookup"><span data-stu-id="653ac-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="653ac-119">此方法旨在由元数据浏览器而不是编译器使用。</span><span class="sxs-lookup"><span data-stu-id="653ac-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="653ac-120">要求</span><span class="sxs-lookup"><span data-stu-id="653ac-120">Requirements</span></span>  
 <span data-ttu-id="653ac-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="653ac-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="653ac-122">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="653ac-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="653ac-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="653ac-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="653ac-124">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="653ac-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653ac-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="653ac-125">See also</span></span>

- [<span data-ttu-id="653ac-126">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="653ac-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="653ac-127">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="653ac-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
