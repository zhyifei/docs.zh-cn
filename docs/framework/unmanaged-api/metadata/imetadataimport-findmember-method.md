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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177284"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="24f38-102">IMetaDataImport::FindMember 方法</span><span class="sxs-lookup"><span data-stu-id="24f38-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="24f38-103">获取指向成员Def令牌的指针，用于指定<xref:System.Type>内容所包含且具有指定名称和元数据签名的字段或方法。</span><span class="sxs-lookup"><span data-stu-id="24f38-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f38-104">语法</span><span class="sxs-lookup"><span data-stu-id="24f38-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24f38-105">parameters</span><span class="sxs-lookup"><span data-stu-id="24f38-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="24f38-106">[在]包含要搜索的成员的类或接口的 TypeDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="24f38-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="24f38-107">如果此值为`mdTokenNil`，则查找将执行全局变量或全局函数。</span><span class="sxs-lookup"><span data-stu-id="24f38-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="24f38-108">[在]要搜索的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="24f38-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="24f38-109">[在]指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="24f38-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="24f38-110">[在]的大小（以字节为单位）。 `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="24f38-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="24f38-111">[出]指向匹配的会员Def令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="24f38-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24f38-112">备注</span><span class="sxs-lookup"><span data-stu-id="24f38-112">Remarks</span></span>  
 <span data-ttu-id="24f38-113">您可以使用其封闭类或接口 （））`td``szName`指定成员，并选择其签名 （）。`pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="24f38-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="24f38-114">类或接口中可能有多个具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="24f38-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="24f38-115">在这种情况下，传递成员的签名以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="24f38-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="24f38-116">传递给的签名`FindMember`必须在当前作用域中生成，因为签名绑定到特定作用域。</span><span class="sxs-lookup"><span data-stu-id="24f38-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="24f38-117">签名可以嵌入标识封闭类或值类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="24f38-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="24f38-118">令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="24f38-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="24f38-119">不能在当前作用域的上下文之外生成运行时签名，并且使用该签名作为输入 到`FindMember`的输入。</span><span class="sxs-lookup"><span data-stu-id="24f38-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="24f38-120">`FindMember`仅查找直接在类或接口中定义的成员;它找不到继承的成员。</span><span class="sxs-lookup"><span data-stu-id="24f38-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24f38-121">`FindMember`是帮助方法。</span><span class="sxs-lookup"><span data-stu-id="24f38-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="24f38-122">它调用[IMetaData 导入：：查找方法](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md);如果该呼叫找不到匹配项，`FindMember`则调用[IMetaDataImport：：FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。</span><span class="sxs-lookup"><span data-stu-id="24f38-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f38-123">要求</span><span class="sxs-lookup"><span data-stu-id="24f38-123">Requirements</span></span>  
 <span data-ttu-id="24f38-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24f38-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f38-125">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="24f38-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24f38-126">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="24f38-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24f38-127">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f38-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f38-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24f38-128">See also</span></span>

- [<span data-ttu-id="24f38-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="24f38-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="24f38-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="24f38-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
