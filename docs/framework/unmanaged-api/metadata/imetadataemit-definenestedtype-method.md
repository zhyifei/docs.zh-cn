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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebd4e9beca315ef8284c915800afec6bdb78c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183230"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="0ddff-102">IMetaDataEmit::DefineNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="0ddff-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="0ddff-103">创建类型定义的元数据签名，则返回`mdTypeDef`的该类型的令牌，并指定定义的类型是所引用的类型的成员`tdEncloser`参数。</span><span class="sxs-lookup"><span data-stu-id="0ddff-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddff-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ddff-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ddff-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ddff-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="0ddff-106">[in]以 unicode 格式的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="0ddff-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="0ddff-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="0ddff-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="0ddff-108">这是一个位掩码的`CorTypeAttr`值。</span><span class="sxs-lookup"><span data-stu-id="0ddff-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="0ddff-109">[in]基类的标记。</span><span class="sxs-lookup"><span data-stu-id="0ddff-109">[in] The token of the base class.</span></span> <span data-ttu-id="0ddff-110">这可以是`mdTypeDef`或`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="0ddff-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="0ddff-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="0ddff-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="0ddff-112">[in]指定此类或接口实现的接口的令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="0ddff-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="0ddff-113">[in]封闭类型的标记。</span><span class="sxs-lookup"><span data-stu-id="0ddff-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="0ddff-114">数组的最后一个元素必须是`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="0ddff-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="0ddff-115">[out]`mdTypeDef`分配标记。</span><span class="sxs-lookup"><span data-stu-id="0ddff-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddff-116">要求</span><span class="sxs-lookup"><span data-stu-id="0ddff-116">Requirements</span></span>  
 <span data-ttu-id="0ddff-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ddff-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddff-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ddff-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ddff-119">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0ddff-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ddff-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddff-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddff-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ddff-121">See also</span></span>

- [<span data-ttu-id="0ddff-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="0ddff-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0ddff-123">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="0ddff-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
