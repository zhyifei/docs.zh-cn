---
title: IMetaDataEmit::GetTokenFromSig 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: d02943f28435fc00aad8e319aa260a24cca5e307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177592"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="c068e-102">IMetaDataEmit::GetTokenFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="c068e-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="c068e-103">获取指定元数据签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="c068e-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c068e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c068e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c068e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="c068e-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="c068e-106">[在]要保留和存储的签名。</span><span class="sxs-lookup"><span data-stu-id="c068e-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="c068e-107">[在]中的`pvSig`字节计数。</span><span class="sxs-lookup"><span data-stu-id="c068e-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="c068e-108">[出]分配的`mdSignature`令牌。</span><span class="sxs-lookup"><span data-stu-id="c068e-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c068e-109">要求</span><span class="sxs-lookup"><span data-stu-id="c068e-109">Requirements</span></span>  
 <span data-ttu-id="c068e-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c068e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c068e-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="c068e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c068e-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c068e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c068e-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c068e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c068e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c068e-114">See also</span></span>

- [<span data-ttu-id="c068e-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="c068e-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c068e-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="c068e-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
