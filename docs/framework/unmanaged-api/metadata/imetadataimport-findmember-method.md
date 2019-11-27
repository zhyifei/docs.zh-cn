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
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437914"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="b50cb-102">IMetaDataImport::FindMember 方法</span><span class="sxs-lookup"><span data-stu-id="b50cb-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="b50cb-103">获取一个指针，该指针指向由指定 <xref:System.Type> 包围且具有指定名称和元数据签名的字段或方法的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="b50cb-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b50cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="b50cb-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b50cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="b50cb-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b50cb-106">中包含要搜索的成员的类或接口的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="b50cb-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="b50cb-107">如果 `mdTokenNil`此值，则将针对全局变量或全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="b50cb-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="b50cb-108">中要搜索的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="b50cb-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b50cb-109">中指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="b50cb-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b50cb-110">中`pvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b50cb-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="b50cb-111">弄指向匹配的 MemberDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="b50cb-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b50cb-112">备注</span><span class="sxs-lookup"><span data-stu-id="b50cb-112">Remarks</span></span>  
 <span data-ttu-id="b50cb-113">使用成员的封闭类或接口（`td`）、其名称（`szName`）以及可选的签名（`pvSigBlob`）来指定成员。</span><span class="sxs-lookup"><span data-stu-id="b50cb-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="b50cb-114">类或接口中可能存在多个具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="b50cb-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="b50cb-115">在这种情况下，传递成员的签名以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="b50cb-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="b50cb-116">传递给 `FindMember` 的签名必须已在当前范围内生成，因为签名将绑定到特定范围。</span><span class="sxs-lookup"><span data-stu-id="b50cb-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="b50cb-117">签名可以嵌入标识封闭类或值类型的标记。</span><span class="sxs-lookup"><span data-stu-id="b50cb-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="b50cb-118">该令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="b50cb-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="b50cb-119">不能在当前范围的上下文之外生成运行时签名，并使用该签名作为输入 `FindMember`。</span><span class="sxs-lookup"><span data-stu-id="b50cb-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="b50cb-120">`FindMember` 仅查找直接在类或接口中定义的成员;它不会查找继承成员。</span><span class="sxs-lookup"><span data-stu-id="b50cb-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b50cb-121">`FindMember` 是一种帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="b50cb-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="b50cb-122">它调用[IMetaDataImport：： FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md);如果该调用找不到匹配项，`FindMember` 将调用[IMetaDataImport：： FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b50cb-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b50cb-123">要求</span><span class="sxs-lookup"><span data-stu-id="b50cb-123">Requirements</span></span>  
 <span data-ttu-id="b50cb-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b50cb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b50cb-125">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b50cb-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b50cb-126">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b50cb-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b50cb-127">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b50cb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b50cb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b50cb-128">See also</span></span>

- [<span data-ttu-id="b50cb-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="b50cb-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b50cb-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="b50cb-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
