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
ms.openlocfilehash: 740dad54bc3a79ff546176abdc35487d89ed8f44
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009244"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="5c631-102">IMetaDataEmit::GetTokenFromSig 方法</span><span class="sxs-lookup"><span data-stu-id="5c631-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="5c631-103">获取指定元数据签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="5c631-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c631-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c631-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c631-105">参数</span><span class="sxs-lookup"><span data-stu-id="5c631-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="5c631-106">中要保持和存储的签名。</span><span class="sxs-lookup"><span data-stu-id="5c631-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="5c631-107">中中的字节数 `pvSig` 。</span><span class="sxs-lookup"><span data-stu-id="5c631-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="5c631-108">弄`mdSignature`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="5c631-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c631-109">要求</span><span class="sxs-lookup"><span data-stu-id="5c631-109">Requirements</span></span>  
 <span data-ttu-id="5c631-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c631-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c631-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5c631-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c631-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5c631-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c631-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c631-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c631-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c631-114">See also</span></span>

- [<span data-ttu-id="5c631-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="5c631-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5c631-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="5c631-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
