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
ms.openlocfilehash: 7410f91a853f3a677a105dc2e12a86d723c9fad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177319"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="f92f4-102">IMetaDataImport::EnumMembersWithName 方法</span><span class="sxs-lookup"><span data-stu-id="f92f4-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="f92f4-103">枚举表示具有指定名称的指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="f92f4-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f92f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f92f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f92f4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f92f4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f92f4-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="f92f4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="f92f4-107">[在]表示要枚举的成员的类型的类型的类型的类型类型。</span><span class="sxs-lookup"><span data-stu-id="f92f4-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="f92f4-108">[在]限制枚举器范围的成员名称。</span><span class="sxs-lookup"><span data-stu-id="f92f4-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="f92f4-109">[出]用于存储成员Def令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="f92f4-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f92f4-110">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="f92f4-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f92f4-111">[出]在 中`rMembers`返回的会员Def令牌的实际数量。</span><span class="sxs-lookup"><span data-stu-id="f92f4-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f92f4-112">备注</span><span class="sxs-lookup"><span data-stu-id="f92f4-112">Remarks</span></span>  
 <span data-ttu-id="f92f4-113">此方法枚举字段和方法，但不枚举属性或事件。</span><span class="sxs-lookup"><span data-stu-id="f92f4-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="f92f4-114">与[IMetaDataImport：：enum成员](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)不同，`EnumMembersWithName`请丢弃没有指定名称的所有字段和成员令牌。</span><span class="sxs-lookup"><span data-stu-id="f92f4-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f92f4-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f92f4-115">Return Value</span></span>  
  
|<span data-ttu-id="f92f4-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f92f4-116">HRESULT</span></span>|<span data-ttu-id="f92f4-117">说明</span><span class="sxs-lookup"><span data-stu-id="f92f4-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f92f4-118">`EnumTypeDefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f92f4-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f92f4-119">没有要枚举的会员Def令牌。</span><span class="sxs-lookup"><span data-stu-id="f92f4-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="f92f4-120">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="f92f4-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f92f4-121">要求</span><span class="sxs-lookup"><span data-stu-id="f92f4-121">Requirements</span></span>  
 <span data-ttu-id="f92f4-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f92f4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f92f4-123">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f92f4-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f92f4-124">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="f92f4-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f92f4-125">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f92f4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92f4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f92f4-126">See also</span></span>

- [<span data-ttu-id="f92f4-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f92f4-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f92f4-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f92f4-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
