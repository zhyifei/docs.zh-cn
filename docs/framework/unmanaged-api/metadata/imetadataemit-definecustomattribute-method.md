---
title: "IMetaDataEmit::DefineCustomAttribute 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineCustomAttribute
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 053601376f8b75e5469a3ef8a3d890a6c6620e28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="359f2-102">IMetaDataEmit::DefineCustomAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="359f2-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="359f2-103">使用指定的元数据签名，要附加到指定的对象，创建的自定义特性的定义并获取指向该自定义特性定义的标记。</span><span class="sxs-lookup"><span data-stu-id="359f2-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="359f2-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="359f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="359f2-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="359f2-106">[in]所有者项标记。</span><span class="sxs-lookup"><span data-stu-id="359f2-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="359f2-107">[in]标识自定义特性的标记。</span><span class="sxs-lookup"><span data-stu-id="359f2-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="359f2-108">[in]指向自定义特性的指针。</span><span class="sxs-lookup"><span data-stu-id="359f2-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="359f2-109">[in]中的字节计数`pCustomAttribute`。</span><span class="sxs-lookup"><span data-stu-id="359f2-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="359f2-110">[out]`mdCustomAttribute`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="359f2-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="359f2-111">惠?</span><span class="sxs-lookup"><span data-stu-id="359f2-111">Requirements</span></span>  
 <span data-ttu-id="359f2-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="359f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="359f2-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="359f2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="359f2-114">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="359f2-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="359f2-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="359f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359f2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="359f2-116">See Also</span></span>  
 [<span data-ttu-id="359f2-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="359f2-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="359f2-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="359f2-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
