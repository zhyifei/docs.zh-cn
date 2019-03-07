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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a58cba0ce4672a479cf5af9467d024a1b1562fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474283"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="89342-102">IMetaDataImport::FindMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="89342-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="89342-103">获取指向成员的 MemberRef 标记的指针，它是引用包含由指定<xref:System.Type>并具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="89342-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89342-104">语法</span><span class="sxs-lookup"><span data-stu-id="89342-104">Syntax</span></span>  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89342-105">参数</span><span class="sxs-lookup"><span data-stu-id="89342-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="89342-106">[in]对类或接口，包含要搜索的成员引用的 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="89342-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="89342-107">如果此值为`mdTokenNil`，在执行查找的全局变量或全局函数引用。</span><span class="sxs-lookup"><span data-stu-id="89342-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="89342-108">[in]要搜索的成员引用的名称。</span><span class="sxs-lookup"><span data-stu-id="89342-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="89342-109">[in]指向成员引用的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="89342-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="89342-110">[in]以字节为单位的大小`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="89342-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="89342-111">[out]指向匹配的 MemberRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="89342-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89342-112">备注</span><span class="sxs-lookup"><span data-stu-id="89342-112">Remarks</span></span>  
 <span data-ttu-id="89342-113">指定使用封闭类或接口的成员 (`td`)，其名称 (`szName`)，并根据需要它的签名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="89342-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="89342-114">签名传递给`FindMemberRef`必须已生成在当前范围内，因为这些签名将绑定到特定的作用域。</span><span class="sxs-lookup"><span data-stu-id="89342-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="89342-115">签名可以嵌入令牌，用于标识封闭类或值类型。</span><span class="sxs-lookup"><span data-stu-id="89342-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="89342-116">令牌的本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="89342-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="89342-117">无法生成上下文的当前作用域外部的运行时签名并使用该签名作为输入`FindMemberRef`。</span><span class="sxs-lookup"><span data-stu-id="89342-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="89342-118">`FindMemberRef` 查找仅直接在类或接口; 中定义的成员引用找不到继承的成员的引用。</span><span class="sxs-lookup"><span data-stu-id="89342-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89342-119">要求</span><span class="sxs-lookup"><span data-stu-id="89342-119">Requirements</span></span>  
 <span data-ttu-id="89342-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89342-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89342-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89342-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89342-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="89342-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89342-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89342-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89342-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="89342-124">See also</span></span>
- [<span data-ttu-id="89342-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="89342-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="89342-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="89342-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
