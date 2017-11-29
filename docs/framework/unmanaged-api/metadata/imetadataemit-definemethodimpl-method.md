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
ms.openlocfilehash: 126cf950b71ed2325006b14927ae95517f7c6dc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="d30d6-102">IMetaDataEmit::DefineMethodImpl 方法</span><span class="sxs-lookup"><span data-stu-id="d30d6-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="d30d6-103">创建实现接口，从继承的方法的定义，并返回到该方法实现定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="d30d6-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d30d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="d30d6-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d30d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="d30d6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d30d6-106">[in]`mdTypedef`令牌的实现的类。</span><span class="sxs-lookup"><span data-stu-id="d30d6-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="d30d6-107">[in]`mdMethodDef`或`mdMethodRef`令牌的代码体。</span><span class="sxs-lookup"><span data-stu-id="d30d6-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="d30d6-108">[in]`mdMethodDef`或`mdMethodRef`正在实现的接口方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="d30d6-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d30d6-109">要求</span><span class="sxs-lookup"><span data-stu-id="d30d6-109">Requirements</span></span>  
 <span data-ttu-id="d30d6-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d30d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d30d6-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d30d6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d30d6-112">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d30d6-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d30d6-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d30d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30d6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d30d6-114">See Also</span></span>  
 [<span data-ttu-id="d30d6-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d30d6-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d30d6-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="d30d6-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
