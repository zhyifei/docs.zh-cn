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
ms.openlocfilehash: 79c9a54a44ae1751cb8b1b57379ccfd6485f6e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448186"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="d1538-102">IMetaDataImport::FindMember 方法</span><span class="sxs-lookup"><span data-stu-id="d1538-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="d1538-103">获取一个指针 MemberDef 标记的字段或方法包含指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="d1538-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1538-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1538-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1538-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1538-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d1538-106">[in]对类或接口包含要搜索的成员的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="d1538-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="d1538-107">如果此值为`mdTokenNil`，对全局变量或全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="d1538-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="d1538-108">[in]要搜索的成员名称。</span><span class="sxs-lookup"><span data-stu-id="d1538-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d1538-109">[in]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="d1538-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d1538-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="d1538-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="d1538-111">[out]指向匹配的 MemberDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="d1538-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1538-112">备注</span><span class="sxs-lookup"><span data-stu-id="d1538-112">Remarks</span></span>  
 <span data-ttu-id="d1538-113">指定使用其封闭类或接口的成员 (`td`)，其名称 (`szName`)，（可选） 及其签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="d1538-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="d1538-114">可能有多个具有相同名称的类或接口中的成员。</span><span class="sxs-lookup"><span data-stu-id="d1538-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="d1538-115">在这种情况下，传递的成员的签名，以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="d1538-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="d1538-116">签名传递给`FindMember`必须已生成在当前范围内，因为签名绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="d1538-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="d1538-117">签名中可以嵌入标识封闭类或值类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="d1538-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="d1538-118">该标记是本地的 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="d1538-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="d1538-119">不能生成上下文之外的当前作用域的运行时签名并使用该签名为的输入`FindMember`。</span><span class="sxs-lookup"><span data-stu-id="d1538-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="d1538-120">`FindMember` 查找直接在类或接口; 中定义的成员找不到继承的成员。</span><span class="sxs-lookup"><span data-stu-id="d1538-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1538-121">`FindMember` 是一个帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="d1538-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="d1538-122">它调用[imetadataimport:: Findmethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); 如果该调用未找到匹配项，`FindMember`然后调用[imetadataimport:: Findfield](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d1538-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1538-123">要求</span><span class="sxs-lookup"><span data-stu-id="d1538-123">Requirements</span></span>  
 <span data-ttu-id="d1538-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1538-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1538-125">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d1538-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1538-126">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d1538-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1538-127">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1538-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1538-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1538-128">See Also</span></span>  
 [<span data-ttu-id="d1538-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d1538-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d1538-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d1538-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
