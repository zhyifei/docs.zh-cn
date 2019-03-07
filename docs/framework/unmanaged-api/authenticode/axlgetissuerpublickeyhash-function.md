---
title: _AxlGetIssuerPublicKeyHash 函数
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 252a3153a49867faf67051be01eeb141fa3ab681
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490341"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="346c6-102">_AxlGetIssuerPublicKeyHash 函数</span><span class="sxs-lookup"><span data-stu-id="346c6-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="346c6-103">检索与用于对指定证书进行签名的私钥关联的公钥的 SHA-1 哈希。</span><span class="sxs-lookup"><span data-stu-id="346c6-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="346c6-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="346c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="346c6-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="346c6-106">[in] CSP 公钥 Blob。</span><span class="sxs-lookup"><span data-stu-id="346c6-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="346c6-107">请参阅[CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="346c6-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="346c6-108">[out] 指向 WCHAR \* 的指针，用于接收十六进制编码的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="346c6-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="346c6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="346c6-109">Return Value</span></span>  
 <span data-ttu-id="346c6-110">如果函数成功，则为 `S_OK`；否则为 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="346c6-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346c6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="346c6-111">See also</span></span>
- [<span data-ttu-id="346c6-112">验证码</span><span class="sxs-lookup"><span data-stu-id="346c6-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
