---
title: _AxlRSAKeyValueToPublicKeyToken 函数
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e09391af9b5d71cfa423b3bf1a2b307117d0dee1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517593"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="27307-102">\_AxlRSAKeyValueToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="27307-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="27307-103">将模数和指数转换为强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="27307-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27307-104">语法</span><span class="sxs-lookup"><span data-stu-id="27307-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a><span data-ttu-id="27307-105">参数</span><span class="sxs-lookup"><span data-stu-id="27307-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="27307-106">[in]Base64 编码的模数 blob (从\<取模 > 元素)。</span><span class="sxs-lookup"><span data-stu-id="27307-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="27307-107">请参阅[CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="27307-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="27307-108">[in]Base64 编码的指数 blob (从\<指数 > 元素)。</span><span class="sxs-lookup"><span data-stu-id="27307-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="27307-109">请参阅[CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="27307-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="27307-110">[out] 指向 WCHAR \* 的指针，用于接收十六进制编码的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="27307-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27307-111">返回值</span><span class="sxs-lookup"><span data-stu-id="27307-111">Return Value</span></span>  
 <span data-ttu-id="27307-112">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="27307-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="27307-113">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="27307-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27307-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="27307-114">See Also</span></span>  
 [<span data-ttu-id="27307-115">验证码</span><span class="sxs-lookup"><span data-stu-id="27307-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
