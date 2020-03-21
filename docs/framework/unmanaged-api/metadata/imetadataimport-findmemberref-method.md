---
title: IMetaDataImport::FindMemberRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175416"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="3819b-102">IMetaDataImport::FindMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="3819b-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="3819b-103">获取指向成员参考的指向成员Ref 令牌的指针，该引用由指定内容<xref:System.Type>所封闭，并且具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="3819b-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3819b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3819b-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3819b-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3819b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3819b-106">[在]包含要搜索的成员引用的类或接口的 TypeRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="3819b-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="3819b-107">如果此值为`mdTokenNil`，则查找将执行全局变量或全局函数引用。</span><span class="sxs-lookup"><span data-stu-id="3819b-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="3819b-108">[在]要搜索的成员引用的名称。</span><span class="sxs-lookup"><span data-stu-id="3819b-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="3819b-109">[在]指向成员引用的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="3819b-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="3819b-110">[在]的大小（以字节为单位）。 `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="3819b-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="3819b-111">[出]指向匹配的会员Ref令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="3819b-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3819b-112">备注</span><span class="sxs-lookup"><span data-stu-id="3819b-112">Remarks</span></span>  
 <span data-ttu-id="3819b-113">您可以使用其封闭类或接口 （））`td``szName`指定成员，并选择其签名 （）。`pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="3819b-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="3819b-114">传递给的签名`FindMemberRef`必须在当前作用域中生成，因为签名绑定到特定作用域。</span><span class="sxs-lookup"><span data-stu-id="3819b-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="3819b-115">签名可以嵌入标识封闭类或值类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="3819b-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="3819b-116">令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="3819b-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="3819b-117">不能在当前作用域的上下文之外生成运行时签名，并且使用该签名作为 输入`FindMemberRef`。</span><span class="sxs-lookup"><span data-stu-id="3819b-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="3819b-118">`FindMemberRef`仅查找直接在类或接口中定义的成员引用;它找不到继承的成员引用。</span><span class="sxs-lookup"><span data-stu-id="3819b-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3819b-119">要求</span><span class="sxs-lookup"><span data-stu-id="3819b-119">Requirements</span></span>  
 <span data-ttu-id="3819b-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3819b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3819b-121">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="3819b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3819b-122">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="3819b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3819b-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3819b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3819b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3819b-124">See also</span></span>

- [<span data-ttu-id="3819b-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3819b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3819b-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3819b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
