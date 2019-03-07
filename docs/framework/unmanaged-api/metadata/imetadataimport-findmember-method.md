---
title: IMetaDataImport::FindMember 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 777d7bf51db3e6984f30e31c46ac115301d13faf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478968"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="cf338-102">IMetaDataImport::FindMember 方法</span><span class="sxs-lookup"><span data-stu-id="cf338-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="cf338-103">获取一个指针 MemberDef 标记的字段或方法都包含由指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="cf338-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf338-104">语法</span><span class="sxs-lookup"><span data-stu-id="cf338-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf338-105">参数</span><span class="sxs-lookup"><span data-stu-id="cf338-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="cf338-106">[in]对类或包含要搜索的成员的接口的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="cf338-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="cf338-107">如果此值为`mdTokenNil`，全局变量或全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="cf338-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="cf338-108">[in]要搜索的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="cf338-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="cf338-109">[in]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="cf338-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="cf338-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="cf338-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="cf338-111">[out]指向匹配的 MemberDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="cf338-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf338-112">备注</span><span class="sxs-lookup"><span data-stu-id="cf338-112">Remarks</span></span>  
 <span data-ttu-id="cf338-113">指定使用封闭类或接口的成员 (`td`)，其名称 (`szName`)，并根据需要它的签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="cf338-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="cf338-114">可能有多个具有相同名称的类或接口中的成员。</span><span class="sxs-lookup"><span data-stu-id="cf338-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="cf338-115">在这种情况下，将传递到唯一的匹配项的成员的签名。</span><span class="sxs-lookup"><span data-stu-id="cf338-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="cf338-116">签名传递给`FindMember`必须已生成在当前范围内，因为这些签名将绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="cf338-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="cf338-117">签名可以嵌入令牌，用于标识封闭类或值类型。</span><span class="sxs-lookup"><span data-stu-id="cf338-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="cf338-118">令牌的本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="cf338-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="cf338-119">不能生成上下文的当前作用域外部的运行时签名并使用该签名一样的输入`FindMember`。</span><span class="sxs-lookup"><span data-stu-id="cf338-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="cf338-120">`FindMember` 查找直接在类或接口; 中定义的成员找不到继承的成员。</span><span class="sxs-lookup"><span data-stu-id="cf338-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf338-121">`FindMember` 是一个帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="cf338-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="cf338-122">它将调用[imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); 如果该调用未找到匹配项，`FindMember`然后调用[imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。</span><span class="sxs-lookup"><span data-stu-id="cf338-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf338-123">要求</span><span class="sxs-lookup"><span data-stu-id="cf338-123">Requirements</span></span>  
 <span data-ttu-id="cf338-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf338-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf338-125">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf338-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf338-126">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cf338-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf338-127">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf338-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf338-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf338-128">See also</span></span>
- [<span data-ttu-id="cf338-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="cf338-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cf338-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="cf338-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
