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
ms.openlocfilehash: f1262181fa745e1b6d3fc48a4ad728c1020705b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434313"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="ed2d6-102">IMetaDataEmit::GetTokenFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="ed2d6-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="ed2d6-103">获取指定元数据签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="ed2d6-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed2d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed2d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed2d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed2d6-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="ed2d6-106">中要保持和存储的签名。</span><span class="sxs-lookup"><span data-stu-id="ed2d6-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="ed2d6-107">中`pvSig`中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="ed2d6-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="ed2d6-108">弄分配 `mdSignature` 标记。</span><span class="sxs-lookup"><span data-stu-id="ed2d6-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed2d6-109">要求</span><span class="sxs-lookup"><span data-stu-id="ed2d6-109">Requirements</span></span>  
 <span data-ttu-id="ed2d6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed2d6-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ed2d6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed2d6-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ed2d6-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed2d6-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed2d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed2d6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed2d6-114">See also</span></span>

- [<span data-ttu-id="ed2d6-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="ed2d6-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ed2d6-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="ed2d6-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
