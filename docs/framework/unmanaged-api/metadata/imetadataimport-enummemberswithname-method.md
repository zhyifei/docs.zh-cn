---
title: IMetaDataImport::EnumMembersWithName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2509945d2799b81e036888d146a51cee87fda09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169840"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="3c2b9-102">IMetaDataImport::EnumMembersWithName 方法</span><span class="sxs-lookup"><span data-stu-id="3c2b9-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="3c2b9-103">枚举表示具有指定名称的指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c2b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c2b9-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c2b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c2b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3c2b9-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="3c2b9-107">[in]表示与要枚举的成员类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="3c2b9-108">[in]成员名称的枚举器的作用域限制。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="3c2b9-109">[out]用于存储 MemberDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c2b9-110">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3c2b9-111">[out]MemberDef 标记中返回的实际数目`rMembers`。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c2b9-112">备注</span><span class="sxs-lookup"><span data-stu-id="3c2b9-112">Remarks</span></span>  
 <span data-ttu-id="3c2b9-113">此方法枚举字段和方法，但不是属性或事件。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="3c2b9-114">与不同[imetadataimport:: Enummembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)，`EnumMembersWithName`放弃所有不具有指定的名称的字段和成员的令牌。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c2b9-115">返回值</span><span class="sxs-lookup"><span data-stu-id="3c2b9-115">Return Value</span></span>  
  
|<span data-ttu-id="3c2b9-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c2b9-116">HRESULT</span></span>|<span data-ttu-id="3c2b9-117">描述</span><span class="sxs-lookup"><span data-stu-id="3c2b9-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` <span data-ttu-id="3c2b9-118">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-118">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c2b9-119">没有要枚举的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="3c2b9-120">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c2b9-121">要求</span><span class="sxs-lookup"><span data-stu-id="3c2b9-121">Requirements</span></span>  
 <span data-ttu-id="3c2b9-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c2b9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c2b9-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c2b9-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c2b9-124">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3c2b9-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3c2b9-125">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3c2b9-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3c2b9-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c2b9-126">See also</span></span>

- [<span data-ttu-id="3c2b9-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3c2b9-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3c2b9-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3c2b9-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
