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
ms.openlocfilehash: 6e73160fb1927560ad381dbb85d03796296ba9a4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434286"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="275be-102">IMetaDataEmit::GetTokenFromTypeSpec 方法</span><span class="sxs-lookup"><span data-stu-id="275be-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="275be-103">Gets a metadata token for the type with the specified metadata signature.</span><span class="sxs-lookup"><span data-stu-id="275be-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="275be-104">语法</span><span class="sxs-lookup"><span data-stu-id="275be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="275be-105">参数</span><span class="sxs-lookup"><span data-stu-id="275be-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="275be-106">[in] The signature being defined.</span><span class="sxs-lookup"><span data-stu-id="275be-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="275be-107">[in] The count of bytes in `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="275be-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="275be-108">[out] The `mdTypeSpec` token assigned.</span><span class="sxs-lookup"><span data-stu-id="275be-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="275be-109">要求</span><span class="sxs-lookup"><span data-stu-id="275be-109">Requirements</span></span>  
 <span data-ttu-id="275be-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="275be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="275be-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="275be-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="275be-112">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="275be-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="275be-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="275be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275be-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="275be-114">See also</span></span>

- [<span data-ttu-id="275be-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="275be-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="275be-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="275be-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
