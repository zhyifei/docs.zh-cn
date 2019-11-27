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
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437954"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="21b31-102">IMetaDataImport::FindMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="21b31-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="21b31-103">获取一个指针，该指针指向成员引用的 MemberRef 标记，该成员引用由指定 <xref:System.Type> 包含并且具有指定的名称和元数据签名。</span><span class="sxs-lookup"><span data-stu-id="21b31-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21b31-104">语法</span><span class="sxs-lookup"><span data-stu-id="21b31-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21b31-105">参数</span><span class="sxs-lookup"><span data-stu-id="21b31-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="21b31-106">中类或接口的 TypeRef 标记，其中包含要搜索的成员引用。</span><span class="sxs-lookup"><span data-stu-id="21b31-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="21b31-107">如果 `mdTokenNil`此值，则将针对全局变量或全局函数引用来执行查找。</span><span class="sxs-lookup"><span data-stu-id="21b31-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="21b31-108">中要搜索的成员引用的名称。</span><span class="sxs-lookup"><span data-stu-id="21b31-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="21b31-109">中指向成员引用的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="21b31-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="21b31-110">中`pvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="21b31-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="21b31-111">弄指向匹配的 MemberRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="21b31-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21b31-112">备注</span><span class="sxs-lookup"><span data-stu-id="21b31-112">Remarks</span></span>  
 <span data-ttu-id="21b31-113">使用成员的封闭类或接口（`td`）、其名称（`szName`）以及可选的签名（`pvSigBlob`）来指定成员。</span><span class="sxs-lookup"><span data-stu-id="21b31-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="21b31-114">传递给 `FindMemberRef` 的签名必须已在当前范围内生成，因为签名将绑定到特定范围。</span><span class="sxs-lookup"><span data-stu-id="21b31-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="21b31-115">签名可以嵌入标识封闭类或值类型的标记。</span><span class="sxs-lookup"><span data-stu-id="21b31-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="21b31-116">该令牌是本地 TypeDef 表中的索引。</span><span class="sxs-lookup"><span data-stu-id="21b31-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="21b31-117">不能在当前范围的上下文之外生成运行时签名，并使用该签名作为 `FindMemberRef`的输入。</span><span class="sxs-lookup"><span data-stu-id="21b31-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="21b31-118">`FindMemberRef` 仅查找直接在类或接口中定义的成员引用;它不会查找继承成员引用。</span><span class="sxs-lookup"><span data-stu-id="21b31-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21b31-119">要求</span><span class="sxs-lookup"><span data-stu-id="21b31-119">Requirements</span></span>  
 <span data-ttu-id="21b31-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21b31-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21b31-121">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="21b31-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21b31-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="21b31-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21b31-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21b31-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b31-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21b31-124">See also</span></span>

- [<span data-ttu-id="21b31-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="21b31-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="21b31-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="21b31-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
