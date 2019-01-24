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
ms.openlocfilehash: 88b8f874400d68110fa5e8fb66ca910b8e7231e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645959"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="e7e38-102">IMetaDataImport::EnumMembers 方法</span><span class="sxs-lookup"><span data-stu-id="e7e38-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="e7e38-103">枚举表示指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="e7e38-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e38-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7e38-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7e38-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7e38-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e7e38-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="e7e38-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="e7e38-107">[in]表示要枚举其成员的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="e7e38-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="e7e38-108">[out]用来保存 MemberDef 标记数组。</span><span class="sxs-lookup"><span data-stu-id="e7e38-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e7e38-109">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="e7e38-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e7e38-110">[out]MemberDef 标记中返回的实际数目`rMembers`。</span><span class="sxs-lookup"><span data-stu-id="e7e38-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7e38-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e7e38-111">Return Value</span></span>  
  
|<span data-ttu-id="e7e38-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7e38-112">HRESULT</span></span>|<span data-ttu-id="e7e38-113">描述</span><span class="sxs-lookup"><span data-stu-id="e7e38-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e7e38-114">`EnumMembers` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e7e38-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e7e38-115">没有要枚举的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="e7e38-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="e7e38-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="e7e38-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e38-117">备注</span><span class="sxs-lookup"><span data-stu-id="e7e38-117">Remarks</span></span>  
 <span data-ttu-id="e7e38-118">枚举的成员的类集合时`EnumMembers`返回只能在类中直接定义的成员。</span><span class="sxs-lookup"><span data-stu-id="e7e38-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="e7e38-119">它不返回任何成员的类继承，即使类提供实现这些继承的成员。</span><span class="sxs-lookup"><span data-stu-id="e7e38-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="e7e38-120">若要枚举继承的成员，调用方必须显式遍历继承链。</span><span class="sxs-lookup"><span data-stu-id="e7e38-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="e7e38-121">请注意，继承链的规则可能会有所不同，具体取决于语言或编译器发出的原始元数据。</span><span class="sxs-lookup"><span data-stu-id="e7e38-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e38-122">要求</span><span class="sxs-lookup"><span data-stu-id="e7e38-122">Requirements</span></span>  
 <span data-ttu-id="e7e38-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e38-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e38-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7e38-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7e38-125">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e7e38-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e38-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e38-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e38-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7e38-127">See also</span></span>
- [<span data-ttu-id="e7e38-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="e7e38-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e7e38-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="e7e38-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
