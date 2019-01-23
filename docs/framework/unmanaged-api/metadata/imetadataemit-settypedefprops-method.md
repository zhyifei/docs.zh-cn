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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7500d7b95426aefc49fea2613ea1572f466defc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496067"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="3163d-102">IMetaDataEmit::SetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="3163d-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="3163d-103">设置由调用之前定义的类型的功能[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3163d-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3163d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3163d-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3163d-105">参数</span><span class="sxs-lookup"><span data-stu-id="3163d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3163d-106">[in]`mdTypeDef`从原始调用获得令牌[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3163d-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="3163d-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="3163d-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="3163d-108">这是一个位掩码的`CorTypeAttr`值。</span><span class="sxs-lookup"><span data-stu-id="3163d-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="3163d-109">[in]`mdToken`的类的基类。</span><span class="sxs-lookup"><span data-stu-id="3163d-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="3163d-110">从以前调用中获取[imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)，或`null`。</span><span class="sxs-lookup"><span data-stu-id="3163d-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="3163d-111">[in]此类型实现的接口的令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="3163d-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="3163d-112">这些`mdTypeRef`使用获取令牌[imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3163d-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="3163d-113">数组的最后一个元素必须是`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="3163d-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3163d-114">要求</span><span class="sxs-lookup"><span data-stu-id="3163d-114">Requirements</span></span>  
 <span data-ttu-id="3163d-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3163d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3163d-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3163d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3163d-117">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3163d-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3163d-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3163d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3163d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3163d-119">See also</span></span>
- [<span data-ttu-id="3163d-120">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="3163d-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3163d-121">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="3163d-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
