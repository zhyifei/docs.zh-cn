---
title: "IMetaDataImport::EnumMembers 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembers
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc17437c18dd7a2cdc2fdabdc714b12f8d91cc7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="61484-102">IMetaDataImport::EnumMembers 方法</span><span class="sxs-lookup"><span data-stu-id="61484-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="61484-103">枚举表示指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="61484-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61484-104">语法</span><span class="sxs-lookup"><span data-stu-id="61484-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61484-105">参数</span><span class="sxs-lookup"><span data-stu-id="61484-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="61484-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="61484-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="61484-107">[in]表示要枚举其成员的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="61484-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="61484-108">[out]用来保存 MemberDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="61484-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="61484-109">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="61484-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="61484-110">[out]在中返回的 MemberDef 标记的实际数`rMembers`。</span><span class="sxs-lookup"><span data-stu-id="61484-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61484-111">返回值</span><span class="sxs-lookup"><span data-stu-id="61484-111">Return Value</span></span>  
  
|<span data-ttu-id="61484-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61484-112">HRESULT</span></span>|<span data-ttu-id="61484-113">描述</span><span class="sxs-lookup"><span data-stu-id="61484-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="61484-114">`EnumMembers`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="61484-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="61484-115">没有要枚举的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="61484-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="61484-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="61484-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61484-117">备注</span><span class="sxs-lookup"><span data-stu-id="61484-117">Remarks</span></span>  
 <span data-ttu-id="61484-118">枚举的成员的类集合时`EnumMembers`返回仅直接在类上定义的成员。</span><span class="sxs-lookup"><span data-stu-id="61484-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="61484-119">即使此类提供这些继承成员的实现，它不返回此类继承，任何成员。</span><span class="sxs-lookup"><span data-stu-id="61484-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="61484-120">若要枚举继承的成员，调用方必须显式引导继承链。</span><span class="sxs-lookup"><span data-stu-id="61484-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="61484-121">请注意，继承链的规则可能会有所不同，具体取决于语言或发出的原始元数据的编译器。</span><span class="sxs-lookup"><span data-stu-id="61484-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61484-122">要求</span><span class="sxs-lookup"><span data-stu-id="61484-122">Requirements</span></span>  
 <span data-ttu-id="61484-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61484-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61484-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61484-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61484-125">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="61484-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61484-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61484-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61484-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61484-127">See Also</span></span>  
 [<span data-ttu-id="61484-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="61484-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="61484-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="61484-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
