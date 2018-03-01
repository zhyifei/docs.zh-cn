---
title: "IMetaDataImport::EnumMethodsWithName 方法"
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
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9f16e66f83925104c4be1e69a476e398f33295a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="7ed63-102">IMetaDataImport::EnumMethodsWithName 方法</span><span class="sxs-lookup"><span data-stu-id="7ed63-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="7ed63-103">枚举具有指定名称并且由指定的 TypeDef 标记所引用的类型定义的方法。</span><span class="sxs-lookup"><span data-stu-id="7ed63-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed63-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ed63-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ed63-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ed63-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7ed63-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="7ed63-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7ed63-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7ed63-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="7ed63-108">[in]表示其方法来枚举的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="7ed63-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="7ed63-109">[in]限制在枚举的作用域的名称。</span><span class="sxs-lookup"><span data-stu-id="7ed63-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="7ed63-110">[out]用于存储的 MethodDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="7ed63-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7ed63-111">[in] `rMethods` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7ed63-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7ed63-112">[out]在中返回的 MethodDef 标记数`rMethods`。</span><span class="sxs-lookup"><span data-stu-id="7ed63-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ed63-113">备注</span><span class="sxs-lookup"><span data-stu-id="7ed63-113">Remarks</span></span>  
 <span data-ttu-id="7ed63-114">此方法枚举字段和方法，但不是属性或事件。</span><span class="sxs-lookup"><span data-stu-id="7ed63-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="7ed63-115">与不同[imetadataimport:: Enummethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)，`EnumMethodsWithName`放弃不具有指定的名称的所有方法令牌。</span><span class="sxs-lookup"><span data-stu-id="7ed63-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ed63-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7ed63-116">Return Value</span></span>  
  
|<span data-ttu-id="7ed63-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ed63-117">HRESULT</span></span>|<span data-ttu-id="7ed63-118">描述</span><span class="sxs-lookup"><span data-stu-id="7ed63-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7ed63-119">`EnumMethodsWithName`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7ed63-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7ed63-120">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="7ed63-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="7ed63-121">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="7ed63-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ed63-122">惠?</span><span class="sxs-lookup"><span data-stu-id="7ed63-122">Requirements</span></span>  
 <span data-ttu-id="7ed63-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed63-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed63-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ed63-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ed63-125">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7ed63-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ed63-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed63-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed63-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed63-127">See Also</span></span>  
 [<span data-ttu-id="7ed63-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7ed63-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7ed63-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7ed63-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
