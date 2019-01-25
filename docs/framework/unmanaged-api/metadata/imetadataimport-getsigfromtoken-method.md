---
title: IMetaDataImport::GetSigFromToken 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b25eb71d78797b5f764cfe4de7abd45f0143fde4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717631"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="dcbfa-102">IMetaDataImport::GetSigFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="dcbfa-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="dcbfa-103">获取与指定标记关联的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="dcbfa-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcbfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="dcbfa-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcbfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="dcbfa-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="dcbfa-106">[in]要返回的二进制元数据签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="dcbfa-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="dcbfa-107">[out]指向返回的元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="dcbfa-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="dcbfa-108">[out]大小 （字节） 的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="dcbfa-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcbfa-109">要求</span><span class="sxs-lookup"><span data-stu-id="dcbfa-109">Requirements</span></span>  
 <span data-ttu-id="dcbfa-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dcbfa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcbfa-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dcbfa-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dcbfa-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dcbfa-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dcbfa-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcbfa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbfa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcbfa-114">See also</span></span>
- [<span data-ttu-id="dcbfa-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="dcbfa-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dcbfa-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="dcbfa-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
