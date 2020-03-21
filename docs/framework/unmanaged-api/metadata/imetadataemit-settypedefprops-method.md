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
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177464"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="9419e-102">IMetaDataEmit::SetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="9419e-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="9419e-103">设置以前调用[IMetaDataEmit：:DefineTypeDef）](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)定义的类型的功能。</span><span class="sxs-lookup"><span data-stu-id="9419e-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9419e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9419e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9419e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9419e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9419e-106">[在]从`mdTypeDef`原始调用[IMetaDataEmit 获得令牌：:DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="9419e-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="9419e-107">[在]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="9419e-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="9419e-108">这是值的`CorTypeAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="9419e-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="9419e-109">[在]基`mdToken`类的 。</span><span class="sxs-lookup"><span data-stu-id="9419e-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="9419e-110">从之前对[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)的调用中获取：:Define`null`导入类型，或 。</span><span class="sxs-lookup"><span data-stu-id="9419e-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="9419e-111">[在]此类型实现的接口的令牌数组。</span><span class="sxs-lookup"><span data-stu-id="9419e-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="9419e-112">这些`mdTypeRef`令牌是使用[IMetaDataEmit：:Define 导入类型](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)获得的。</span><span class="sxs-lookup"><span data-stu-id="9419e-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="9419e-113">数组的最后一个元素必须是`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="9419e-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9419e-114">要求</span><span class="sxs-lookup"><span data-stu-id="9419e-114">Requirements</span></span>  
 <span data-ttu-id="9419e-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9419e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9419e-116">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="9419e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9419e-117">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9419e-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9419e-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9419e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9419e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9419e-119">See also</span></span>

- [<span data-ttu-id="9419e-120">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="9419e-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9419e-121">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="9419e-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
