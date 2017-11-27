---
title: "IMetaDataImport::EnumSignatures 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumSignatures
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25fb32b0780dc91157d39ece37f93d7abd582cf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="ee720-102">IMetaDataImport::EnumSignatures 方法</span><span class="sxs-lookup"><span data-stu-id="ee720-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="ee720-103">枚举当前范围内表示独立签名的 Signature 标记。</span><span class="sxs-lookup"><span data-stu-id="ee720-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee720-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee720-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee720-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee720-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ee720-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="ee720-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ee720-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ee720-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="ee720-108">[out]用于存储签名令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="ee720-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ee720-109">[in] `rSignatures` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ee720-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="ee720-110">[out]签名令牌中返回的数目`rSignatures`。</span><span class="sxs-lookup"><span data-stu-id="ee720-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee720-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ee720-111">Return Value</span></span>  
  
|<span data-ttu-id="ee720-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee720-112">HRESULT</span></span>|<span data-ttu-id="ee720-113">描述</span><span class="sxs-lookup"><span data-stu-id="ee720-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ee720-114">`EnumSignatures`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ee720-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ee720-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="ee720-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ee720-116">在这种情况下，`pcSignatures`为零。</span><span class="sxs-lookup"><span data-stu-id="ee720-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee720-117">备注</span><span class="sxs-lookup"><span data-stu-id="ee720-117">Remarks</span></span>  
 <span data-ttu-id="ee720-118">签名令牌由[imetadataemit:: Gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ee720-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee720-119">要求</span><span class="sxs-lookup"><span data-stu-id="ee720-119">Requirements</span></span>  
 <span data-ttu-id="ee720-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee720-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee720-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee720-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee720-122">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ee720-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee720-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee720-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee720-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee720-124">See Also</span></span>  
 [<span data-ttu-id="ee720-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ee720-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ee720-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="ee720-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
