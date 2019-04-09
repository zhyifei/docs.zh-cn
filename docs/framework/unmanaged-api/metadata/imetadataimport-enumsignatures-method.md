---
title: IMetaDataImport::EnumSignatures 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 193abe173b259ff2679642e229fce96151e37872
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179670"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="27198-102">IMetaDataImport::EnumSignatures 方法</span><span class="sxs-lookup"><span data-stu-id="27198-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="27198-103">枚举当前范围内表示独立签名的 Signature 标记。</span><span class="sxs-lookup"><span data-stu-id="27198-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27198-104">语法</span><span class="sxs-lookup"><span data-stu-id="27198-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27198-105">参数</span><span class="sxs-lookup"><span data-stu-id="27198-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="27198-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="27198-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="27198-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="27198-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="27198-108">[out]用于存储签名令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="27198-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="27198-109">[in] `rSignatures` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="27198-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="27198-110">[out]签名令牌中返回的数目`rSignatures`。</span><span class="sxs-lookup"><span data-stu-id="27198-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27198-111">返回值</span><span class="sxs-lookup"><span data-stu-id="27198-111">Return Value</span></span>  
  
|<span data-ttu-id="27198-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27198-112">HRESULT</span></span>|<span data-ttu-id="27198-113">描述</span><span class="sxs-lookup"><span data-stu-id="27198-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures` <span data-ttu-id="27198-114">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="27198-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="27198-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="27198-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="27198-116">在这种情况下，`pcSignatures`为零。</span><span class="sxs-lookup"><span data-stu-id="27198-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27198-117">备注</span><span class="sxs-lookup"><span data-stu-id="27198-117">Remarks</span></span>  
 <span data-ttu-id="27198-118">签名令牌创建的[imetadataemit:: Gettokenfromsig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="27198-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27198-119">要求</span><span class="sxs-lookup"><span data-stu-id="27198-119">Requirements</span></span>  
 <span data-ttu-id="27198-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27198-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27198-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27198-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27198-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="27198-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="27198-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="27198-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27198-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="27198-124">See also</span></span>

- [<span data-ttu-id="27198-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="27198-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="27198-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="27198-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
