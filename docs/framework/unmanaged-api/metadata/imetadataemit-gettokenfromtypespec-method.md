---
title: IMetaDataEmit::GetTokenFromTypeSpec 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 8c609d730297881c0ac20dca8569f0e9492638e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175715"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="0a8c4-102">IMetaDataEmit::GetTokenFromTypeSpec 方法</span><span class="sxs-lookup"><span data-stu-id="0a8c4-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="0a8c4-103">使用指定的元数据签名获取类型的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="0a8c4-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a8c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a8c4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="0a8c4-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="0a8c4-106">[在]正在定义的签名。</span><span class="sxs-lookup"><span data-stu-id="0a8c4-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="0a8c4-107">[在]中的`pvSig`字节计数。</span><span class="sxs-lookup"><span data-stu-id="0a8c4-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="0a8c4-108">[出]分配的`mdTypeSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="0a8c4-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a8c4-109">要求</span><span class="sxs-lookup"><span data-stu-id="0a8c4-109">Requirements</span></span>  
 <span data-ttu-id="0a8c4-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8c4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a8c4-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="0a8c4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a8c4-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0a8c4-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a8c4-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a8c4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8c4-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a8c4-114">See also</span></span>

- [<span data-ttu-id="0a8c4-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="0a8c4-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0a8c4-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="0a8c4-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
