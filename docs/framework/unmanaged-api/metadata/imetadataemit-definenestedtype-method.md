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
ms.openlocfilehash: 5d985e22ba77053127610445374b8c13ca6b97f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431703"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="8701c-102">IMetaDataEmit::DefineNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="8701c-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="8701c-103">创建类型定义的元数据签名，返回该类型的 `mdTypeDef` 标记，并指定该定义类型是 `tdEncloser` 参数所引用的类型的成员。</span><span class="sxs-lookup"><span data-stu-id="8701c-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8701c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8701c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8701c-105">参数</span><span class="sxs-lookup"><span data-stu-id="8701c-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="8701c-106">中Unicode 中类型的名称。</span><span class="sxs-lookup"><span data-stu-id="8701c-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="8701c-107">[in] `TypeDef` 特性。</span><span class="sxs-lookup"><span data-stu-id="8701c-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="8701c-108">这是 `CorTypeAttr` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8701c-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="8701c-109">中基类的标记。</span><span class="sxs-lookup"><span data-stu-id="8701c-109">[in] The token of the base class.</span></span> <span data-ttu-id="8701c-110">这是 `mdTypeDef` 或 `mdTypeRef` 令牌。</span><span class="sxs-lookup"><span data-stu-id="8701c-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="8701c-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="8701c-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="8701c-112">中标记的数组，该数组指定此类或接口实现的接口。</span><span class="sxs-lookup"><span data-stu-id="8701c-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="8701c-113">中封闭类型的标记。</span><span class="sxs-lookup"><span data-stu-id="8701c-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="8701c-114">数组的最后一个元素必须是 `mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="8701c-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="8701c-115">弄分配 `mdTypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="8701c-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8701c-116">要求</span><span class="sxs-lookup"><span data-stu-id="8701c-116">Requirements</span></span>  
 <span data-ttu-id="8701c-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8701c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8701c-118">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8701c-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8701c-119">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8701c-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8701c-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8701c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8701c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8701c-121">See also</span></span>

- [<span data-ttu-id="8701c-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8701c-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8701c-123">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="8701c-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
