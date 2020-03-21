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
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175481"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="612bb-102">IMetaDataImport::EnumMembers 方法</span><span class="sxs-lookup"><span data-stu-id="612bb-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="612bb-103">枚举表示指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="612bb-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="612bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="612bb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="612bb-105">parameters</span><span class="sxs-lookup"><span data-stu-id="612bb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="612bb-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="612bb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="612bb-107">[在]表示要枚举其成员的类型的类型的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="612bb-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="612bb-108">[出]用于保存成员Def令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="612bb-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="612bb-109">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="612bb-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="612bb-110">[出]在 中`rMembers`返回的会员Def令牌的实际数量。</span><span class="sxs-lookup"><span data-stu-id="612bb-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="612bb-111">返回值</span><span class="sxs-lookup"><span data-stu-id="612bb-111">Return Value</span></span>  
  
|<span data-ttu-id="612bb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="612bb-112">HRESULT</span></span>|<span data-ttu-id="612bb-113">说明</span><span class="sxs-lookup"><span data-stu-id="612bb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="612bb-114">`EnumMembers`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="612bb-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="612bb-115">没有要枚举的会员Def令牌。</span><span class="sxs-lookup"><span data-stu-id="612bb-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="612bb-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="612bb-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="612bb-117">备注</span><span class="sxs-lookup"><span data-stu-id="612bb-117">Remarks</span></span>  
 <span data-ttu-id="612bb-118">枚举类成员的集合时，`EnumMembers`仅返回直接在类上定义的成员（字段和方法，**但不包括**属性或事件）。</span><span class="sxs-lookup"><span data-stu-id="612bb-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="612bb-119">它不返回类继承的任何成员，即使类为这些继承成员提供了实现也是如此。</span><span class="sxs-lookup"><span data-stu-id="612bb-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="612bb-120">要枚举继承的成员，调用方必须显式遍历继承链。</span><span class="sxs-lookup"><span data-stu-id="612bb-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="612bb-121">请注意，继承链的规则可能因发出原始元数据的语言或编译器而异。</span><span class="sxs-lookup"><span data-stu-id="612bb-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="612bb-122">属性和事件不由 枚举`EnumMembers`枚举。</span><span class="sxs-lookup"><span data-stu-id="612bb-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="612bb-123">要枚举这些，请使用[枚举属性](imetadataimport-enumproperties-method.md)或[枚举事件](imetadataimport-enumevents-method.md)。</span><span class="sxs-lookup"><span data-stu-id="612bb-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="612bb-124">要求</span><span class="sxs-lookup"><span data-stu-id="612bb-124">Requirements</span></span>  
 <span data-ttu-id="612bb-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="612bb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="612bb-126">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="612bb-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="612bb-127">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="612bb-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="612bb-128">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="612bb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612bb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="612bb-129">See also</span></span>

- [<span data-ttu-id="612bb-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="612bb-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="612bb-131">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="612bb-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
