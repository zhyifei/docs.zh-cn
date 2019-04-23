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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09256deafdb42847f369664ec8c4bc96d72424d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177601"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="51abc-102">IMetaDataEmit::GetTokenFromTypeSpec 方法</span><span class="sxs-lookup"><span data-stu-id="51abc-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="51abc-103">获取具有指定的元数据签名的类型的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="51abc-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51abc-104">语法</span><span class="sxs-lookup"><span data-stu-id="51abc-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51abc-105">参数</span><span class="sxs-lookup"><span data-stu-id="51abc-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="51abc-106">[in]正在定义的签名。</span><span class="sxs-lookup"><span data-stu-id="51abc-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="51abc-107">[in]中的字节计数`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="51abc-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="51abc-108">[out]`mdTypeSpec`分配标记。</span><span class="sxs-lookup"><span data-stu-id="51abc-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51abc-109">要求</span><span class="sxs-lookup"><span data-stu-id="51abc-109">Requirements</span></span>  
 <span data-ttu-id="51abc-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51abc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51abc-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51abc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51abc-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="51abc-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51abc-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51abc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51abc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="51abc-114">See also</span></span>

- [<span data-ttu-id="51abc-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="51abc-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="51abc-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="51abc-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
