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
ms.openlocfilehash: 4eefb7ec1e7d0d130ec64531a59d1d5bbce04963
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968920"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="b1a00-102">IMetaDataImport::FindMember 方法</span><span class="sxs-lookup"><span data-stu-id="b1a00-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="b1a00-103">获取一个指针, 该指针指向由指定的和具有指定名称和元数据<xref:System.Type>签名的指定的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="b1a00-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a00-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1a00-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1a00-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1a00-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b1a00-106">中包含要搜索的成员的类或接口的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="b1a00-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="b1a00-107">如果此值为`mdTokenNil`, 则对全局变量或全局函数执行查找。</span><span class="sxs-lookup"><span data-stu-id="b1a00-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="b1a00-108">中要搜索的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="b1a00-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b1a00-109">中指向成员的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="b1a00-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b1a00-110">中的大小 (以字节`pvSigBlob`为单位)。</span><span class="sxs-lookup"><span data-stu-id="b1a00-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="b1a00-111">弄指向匹配的 MemberDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="b1a00-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1a00-112">备注</span><span class="sxs-lookup"><span data-stu-id="b1a00-112">Remarks</span></span>  
 <span data-ttu-id="b1a00-113">使用成员的封闭类或接口 (`td`)、其名称 (`szName`) 和 (可选) 的签名 (`pvSigBlob`) 来指定成员。</span><span class="sxs-lookup"><span data-stu-id="b1a00-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="b1a00-114">类或接口中可能存在多个具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="b1a00-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="b1a00-115">在这种情况下, 传递成员的签名以查找唯一匹配项。</span><span class="sxs-lookup"><span data-stu-id="b1a00-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="b1a00-116">传递给`FindMember`的签名必须已在当前范围内生成, 因为签名将绑定到特定范围。</span><span class="sxs-lookup"><span data-stu-id="b1a00-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="b1a00-117">签名可以嵌入标识封闭类或值类型的标记。</span><span class="sxs-lookup"><span data-stu-id="b1a00-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="b1a00-118">该令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="b1a00-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="b1a00-119">不能在当前范围的上下文之外生成运行时签名, 并将该签名用作输入以输入到`FindMember`。</span><span class="sxs-lookup"><span data-stu-id="b1a00-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="b1a00-120">`FindMember`仅查找直接在类或接口中定义的成员;它不会查找继承成员。</span><span class="sxs-lookup"><span data-stu-id="b1a00-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1a00-121">`FindMember`是一个帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="b1a00-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="b1a00-122">它调用[IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md);如果该调用找不到匹配项, `FindMember`则调用[IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a00-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1a00-123">要求</span><span class="sxs-lookup"><span data-stu-id="b1a00-123">Requirements</span></span>  
 <span data-ttu-id="b1a00-124">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a00-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1a00-125">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b1a00-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1a00-126">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b1a00-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1a00-127">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1a00-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a00-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1a00-128">See also</span></span>

- [<span data-ttu-id="b1a00-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="b1a00-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b1a00-130">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="b1a00-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
