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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177601"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="3bde7-102">IMetaDataEmit::GetTokenFromTypeSpec 方法</span><span class="sxs-lookup"><span data-stu-id="3bde7-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="3bde7-103">获取具有指定的元数据签名的类型的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="3bde7-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bde7-104">语法</span><span class="sxs-lookup"><span data-stu-id="3bde7-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bde7-105">参数</span><span class="sxs-lookup"><span data-stu-id="3bde7-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="3bde7-106">[in]正在定义的签名。</span><span class="sxs-lookup"><span data-stu-id="3bde7-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="3bde7-107">[in]中的字节计数`pvSig`。</span><span class="sxs-lookup"><span data-stu-id="3bde7-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="3bde7-108">[out]`mdTypeSpec`分配标记。</span><span class="sxs-lookup"><span data-stu-id="3bde7-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bde7-109">要求</span><span class="sxs-lookup"><span data-stu-id="3bde7-109">Requirements</span></span>  
 <span data-ttu-id="3bde7-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3bde7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bde7-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3bde7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bde7-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3bde7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3bde7-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3bde7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3bde7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bde7-114">See also</span></span>

- [<span data-ttu-id="3bde7-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="3bde7-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3bde7-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="3bde7-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
