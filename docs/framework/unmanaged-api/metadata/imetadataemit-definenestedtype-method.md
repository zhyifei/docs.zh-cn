---
title: IMetaDataEmit::DefineNestedType 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175806"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="2a3ba-102">IMetaDataEmit::DefineNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="2a3ba-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="2a3ba-103">创建类型定义的元数据签名，返回该类型的`mdTypeDef`令牌，并指定定义的类型是`tdEncloser`参数引用的类型的成员。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a3ba-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3ba-105">parameters</span><span class="sxs-lookup"><span data-stu-id="2a3ba-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="2a3ba-106">[在]Unicode 中类型的名称。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="2a3ba-107">[在]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="2a3ba-108">这是值的`CorTypeAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="2a3ba-109">[在]基类的令牌。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-109">[in] The token of the base class.</span></span> <span data-ttu-id="2a3ba-110">这是 或`mdTypeDef``mdTypeRef`标记。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="2a3ba-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="2a3ba-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="2a3ba-112">[在]指定此类或接口实现的接口的令牌数组。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="2a3ba-113">[在]封闭类型的标记。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="2a3ba-114">数组的最后一个元素必须是`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="2a3ba-115">[出]分配的`mdTypeDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3ba-116">要求</span><span class="sxs-lookup"><span data-stu-id="2a3ba-116">Requirements</span></span>  
 <span data-ttu-id="2a3ba-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a3ba-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3ba-118">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="2a3ba-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a3ba-119">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2a3ba-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3ba-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3ba-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3ba-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a3ba-121">See also</span></span>

- [<span data-ttu-id="2a3ba-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="2a3ba-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2a3ba-123">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="2a3ba-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
