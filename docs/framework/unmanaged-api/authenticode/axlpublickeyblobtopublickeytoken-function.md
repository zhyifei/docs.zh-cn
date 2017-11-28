---
title: "_AxlPublicKeyBlobToPublicKeyToken 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlPublicKeyBlobToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25a6a78fad95b894e82a75159458f25264f0ee0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="7ee57-102">_AxlPublicKeyBlobToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="7ee57-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="7ee57-103">从 CSP PUBLICKEYBLOB 格式计算强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="7ee57-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee57-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ee57-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ee57-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ee57-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="7ee57-106">[in] CSP 公钥 Blob。</span><span class="sxs-lookup"><span data-stu-id="7ee57-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="7ee57-107">[out] 指向 WCHAR * 的指针，用于接收十六进制编码的公钥哈希。</span><span class="sxs-lookup"><span data-stu-id="7ee57-107">[out] A pointer to WCHAR * to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ee57-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7ee57-108">Return Value</span></span>  
 <span data-ttu-id="7ee57-109">如果函数成功，则为 `S_OK`；否则为 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="7ee57-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee57-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee57-110">See Also</span></span>  
 [<span data-ttu-id="7ee57-111">验证码</span><span class="sxs-lookup"><span data-stu-id="7ee57-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
