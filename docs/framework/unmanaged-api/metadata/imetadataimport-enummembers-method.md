---
title: IMetaDataImport::EnumMembers 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46ee8c62861a62ac044f295f7da082756d87347b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447628"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="cf4bb-102">IMetaDataImport::EnumMembers 方法</span><span class="sxs-lookup"><span data-stu-id="cf4bb-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="cf4bb-103">枚举表示指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf4bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="cf4bb-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf4bb-105">参数</span><span class="sxs-lookup"><span data-stu-id="cf4bb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cf4bb-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="cf4bb-107">[in]表示要枚举其成员的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="cf4bb-108">[out]用来保存 MemberDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cf4bb-109">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cf4bb-110">[out]在中返回的 MemberDef 标记的实际数`rMembers`。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf4bb-111">返回值</span><span class="sxs-lookup"><span data-stu-id="cf4bb-111">Return Value</span></span>  
  
|<span data-ttu-id="cf4bb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf4bb-112">HRESULT</span></span>|<span data-ttu-id="cf4bb-113">描述</span><span class="sxs-lookup"><span data-stu-id="cf4bb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf4bb-114">`EnumMembers` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cf4bb-115">没有要枚举的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="cf4bb-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf4bb-117">备注</span><span class="sxs-lookup"><span data-stu-id="cf4bb-117">Remarks</span></span>  
 <span data-ttu-id="cf4bb-118">枚举的成员的类集合时`EnumMembers`返回仅直接在类上定义的成员。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="cf4bb-119">即使此类提供这些继承成员的实现，它不返回此类继承，任何成员。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="cf4bb-120">若要枚举继承的成员，调用方必须显式引导继承链。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="cf4bb-121">请注意，继承链的规则可能会有所不同，具体取决于语言或发出的原始元数据的编译器。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf4bb-122">要求</span><span class="sxs-lookup"><span data-stu-id="cf4bb-122">Requirements</span></span>  
 <span data-ttu-id="cf4bb-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf4bb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf4bb-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf4bb-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf4bb-125">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cf4bb-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf4bb-126">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf4bb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4bb-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf4bb-127">See Also</span></span>  
 [<span data-ttu-id="cf4bb-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="cf4bb-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="cf4bb-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="cf4bb-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
