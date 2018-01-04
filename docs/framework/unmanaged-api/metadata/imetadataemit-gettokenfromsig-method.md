---
title: "IMetaDataEmit::GetTokenFromSig 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetTokenFromSig
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df454b8dd95839f4cabe3c725e206f3683437ec4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="91ed7-102">IMetaDataEmit::GetTokenFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="91ed7-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="91ed7-103">获取指定的元数据签名令牌。</span><span class="sxs-lookup"><span data-stu-id="91ed7-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ed7-104">语法</span><span class="sxs-lookup"><span data-stu-id="91ed7-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91ed7-105">参数</span><span class="sxs-lookup"><span data-stu-id="91ed7-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="91ed7-106">[in]要被持久化并在存储的签名。</span><span class="sxs-lookup"><span data-stu-id="91ed7-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="91ed7-107">[in]中的字节计数`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="91ed7-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="91ed7-108">[out]`mdSignature`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="91ed7-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91ed7-109">惠?</span><span class="sxs-lookup"><span data-stu-id="91ed7-109">Requirements</span></span>  
 <span data-ttu-id="91ed7-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91ed7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91ed7-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="91ed7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91ed7-112">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="91ed7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91ed7-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91ed7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ed7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="91ed7-114">See Also</span></span>  
 [<span data-ttu-id="91ed7-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="91ed7-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="91ed7-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="91ed7-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
