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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4be12e46851b11a5e6db60c351094a356fa61f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082940"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="8e8ea-102">IMetaDataImport::EnumUserStrings 方法</span><span class="sxs-lookup"><span data-stu-id="8e8ea-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="8e8ea-103">枚举表示当前元数据范围内的硬编码字符串的 String 标记。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e8ea-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e8ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e8ea-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8e8ea-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8e8ea-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="8e8ea-108">[out]用于存储的字符串标记的数组。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8e8ea-109">[in] `rStrings` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="8e8ea-110">[out]字符串中返回的标记数`rStrings`。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e8ea-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8e8ea-111">Return Value</span></span>  
  
|<span data-ttu-id="8e8ea-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e8ea-112">HRESULT</span></span>|<span data-ttu-id="8e8ea-113">描述</span><span class="sxs-lookup"><span data-stu-id="8e8ea-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumUserStrings` <span data-ttu-id="8e8ea-114">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8e8ea-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8e8ea-116">在这种情况下，`pcStrings`为零。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e8ea-117">备注</span><span class="sxs-lookup"><span data-stu-id="8e8ea-117">Remarks</span></span>  
 <span data-ttu-id="8e8ea-118">创建的字符串标记[imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="8e8ea-119">此方法旨在由元数据浏览器中，而不是由编译器使用。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e8ea-120">要求</span><span class="sxs-lookup"><span data-stu-id="8e8ea-120">Requirements</span></span>  
 <span data-ttu-id="8e8ea-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e8ea-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e8ea-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8e8ea-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e8ea-123">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8e8ea-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8e8ea-124">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8e8ea-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e8ea-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e8ea-125">See also</span></span>

- [<span data-ttu-id="8e8ea-126">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8e8ea-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8e8ea-127">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="8e8ea-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
