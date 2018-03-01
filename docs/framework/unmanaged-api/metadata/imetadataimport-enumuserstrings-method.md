---
title: "IMetaDataImport::EnumUserStrings 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3d9c802318203db2ccd6043cded3c7730b18b0cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="645aa-102">IMetaDataImport::EnumUserStrings 方法</span><span class="sxs-lookup"><span data-stu-id="645aa-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="645aa-103">枚举表示当前元数据范围内的硬编码字符串的 String 标记。</span><span class="sxs-lookup"><span data-stu-id="645aa-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="645aa-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="645aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="645aa-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="645aa-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="645aa-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="645aa-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="645aa-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="645aa-108">[out]用于存储字符串标记数组。</span><span class="sxs-lookup"><span data-stu-id="645aa-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="645aa-109">[in] `rStrings` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="645aa-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="645aa-110">[out]在中返回的字符串标记的数目`rStrings`。</span><span class="sxs-lookup"><span data-stu-id="645aa-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="645aa-111">返回值</span><span class="sxs-lookup"><span data-stu-id="645aa-111">Return Value</span></span>  
  
|<span data-ttu-id="645aa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="645aa-112">HRESULT</span></span>|<span data-ttu-id="645aa-113">描述</span><span class="sxs-lookup"><span data-stu-id="645aa-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="645aa-114">`EnumUserStrings`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="645aa-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="645aa-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="645aa-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="645aa-116">在这种情况下，`pcStrings`为零。</span><span class="sxs-lookup"><span data-stu-id="645aa-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="645aa-117">备注</span><span class="sxs-lookup"><span data-stu-id="645aa-117">Remarks</span></span>  
 <span data-ttu-id="645aa-118">字符串令牌由[imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="645aa-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="645aa-119">此方法旨在按元数据浏览器中，而不是由编译器使用。</span><span class="sxs-lookup"><span data-stu-id="645aa-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645aa-120">惠?</span><span class="sxs-lookup"><span data-stu-id="645aa-120">Requirements</span></span>  
 <span data-ttu-id="645aa-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="645aa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="645aa-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="645aa-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="645aa-123">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="645aa-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="645aa-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="645aa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645aa-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="645aa-125">See Also</span></span>  
 [<span data-ttu-id="645aa-126">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="645aa-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="645aa-127">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="645aa-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
