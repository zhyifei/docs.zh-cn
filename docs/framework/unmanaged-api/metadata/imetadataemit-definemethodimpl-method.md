---
title: "IMetaDataEmit::DefineMethodImpl 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5bf16c51a241a01f18aae84f8b3bb7554f08b87c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="6baec-102">IMetaDataEmit::DefineMethodImpl 方法</span><span class="sxs-lookup"><span data-stu-id="6baec-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="6baec-103">创建实现接口，从继承的方法的定义，并返回到该方法实现定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="6baec-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6baec-104">语法</span><span class="sxs-lookup"><span data-stu-id="6baec-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6baec-105">参数</span><span class="sxs-lookup"><span data-stu-id="6baec-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6baec-106">[in]`mdTypedef`令牌的实现的类。</span><span class="sxs-lookup"><span data-stu-id="6baec-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="6baec-107">[in]`mdMethodDef`或`mdMethodRef`令牌的代码体。</span><span class="sxs-lookup"><span data-stu-id="6baec-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="6baec-108">[in]`mdMethodDef`或`mdMethodRef`正在实现的接口方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="6baec-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6baec-109">惠?</span><span class="sxs-lookup"><span data-stu-id="6baec-109">Requirements</span></span>  
 <span data-ttu-id="6baec-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6baec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6baec-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6baec-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6baec-112">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6baec-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6baec-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6baec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6baec-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6baec-114">See Also</span></span>  
 [<span data-ttu-id="6baec-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="6baec-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="6baec-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="6baec-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
