---
title: IMetaDataEmit::SetTypeDefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447727"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="23caf-102">IMetaDataEmit::SetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="23caf-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="23caf-103">设置由之前调用[IMetaDataEmit：:D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)定义的类型的功能。</span><span class="sxs-lookup"><span data-stu-id="23caf-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23caf-104">语法</span><span class="sxs-lookup"><span data-stu-id="23caf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23caf-105">参数</span><span class="sxs-lookup"><span data-stu-id="23caf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="23caf-106">中从对[IMetaDataEmit：:D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)的原始调用获取的 `mdTypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="23caf-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="23caf-107">[in] `TypeDef` 特性。</span><span class="sxs-lookup"><span data-stu-id="23caf-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="23caf-108">这是 `CorTypeAttr` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="23caf-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="23caf-109">中基类的 `mdToken`。</span><span class="sxs-lookup"><span data-stu-id="23caf-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="23caf-110">从之前对 IMetaDataEmit 的调用中获取[：:D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)或 `null`。</span><span class="sxs-lookup"><span data-stu-id="23caf-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="23caf-111">中此类型实现的接口的标记数组。</span><span class="sxs-lookup"><span data-stu-id="23caf-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="23caf-112">这些 `mdTypeRef` 令牌是使用[IMetaDataEmit：:D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)获取的。</span><span class="sxs-lookup"><span data-stu-id="23caf-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="23caf-113">数组的最后一个元素必须是 `mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="23caf-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23caf-114">要求</span><span class="sxs-lookup"><span data-stu-id="23caf-114">Requirements</span></span>  
 <span data-ttu-id="23caf-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23caf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23caf-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="23caf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23caf-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="23caf-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23caf-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23caf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23caf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23caf-119">See also</span></span>

- [<span data-ttu-id="23caf-120">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="23caf-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="23caf-121">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="23caf-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
