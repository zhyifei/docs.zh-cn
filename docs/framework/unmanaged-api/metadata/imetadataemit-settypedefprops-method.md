---
title: "IMetaDataEmit::SetTypeDefProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 50f92d0ff307621695887ee7a0af2d4d19985f51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="af81b-102">IMetaDataEmit::SetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="af81b-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="af81b-103">设置由调用定义的类型的功能[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="af81b-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af81b-104">语法</span><span class="sxs-lookup"><span data-stu-id="af81b-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af81b-105">参数</span><span class="sxs-lookup"><span data-stu-id="af81b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="af81b-106">[in]`mdTypeDef`从原始调用获得的令牌[imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)。</span><span class="sxs-lookup"><span data-stu-id="af81b-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="af81b-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="af81b-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="af81b-108">这是一个位掩码的`CorTypeAttr`值。</span><span class="sxs-lookup"><span data-stu-id="af81b-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="af81b-109">[in]`mdToken`的基类。</span><span class="sxs-lookup"><span data-stu-id="af81b-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="af81b-110">从上次调用获取[imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)，或`null`。</span><span class="sxs-lookup"><span data-stu-id="af81b-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="af81b-111">[in]此类型实现的接口的令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="af81b-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="af81b-112">这些`mdTypeRef`令牌获取使用[imetadataemit:: Defineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="af81b-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="af81b-113">数组的最后一个元素是必须是`mdTokenNil`。</span><span class="sxs-lookup"><span data-stu-id="af81b-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af81b-114">要求</span><span class="sxs-lookup"><span data-stu-id="af81b-114">Requirements</span></span>  
 <span data-ttu-id="af81b-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af81b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af81b-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af81b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af81b-117">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="af81b-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af81b-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af81b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af81b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af81b-119">See Also</span></span>  
 [<span data-ttu-id="af81b-120">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="af81b-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="af81b-121">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="af81b-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
