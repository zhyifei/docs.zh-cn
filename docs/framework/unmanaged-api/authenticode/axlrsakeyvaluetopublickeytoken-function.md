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
ms.openlocfilehash: 7ef73f0f7599fdff887437756a5995591fd8ec89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402403"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="b9ecf-102">_AxlRSAKeyValueToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="b9ecf-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="b9ecf-103">将模数和指数转换为强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ecf-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9ecf-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ecf-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9ecf-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="b9ecf-106">[in]Base64 编码的模数 blob (从\<取模 > 元素)。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="b9ecf-107">请参阅[CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="b9ecf-108">[in]Base64 编码的指数 blob (从\<指数 > 元素)。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="b9ecf-109">请参阅[CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="b9ecf-110">[out] 指向 WCHAR \* 的指针，用于接收十六进制编码的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9ecf-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b9ecf-111">Return Value</span></span>  
 <span data-ttu-id="b9ecf-112">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b9ecf-113">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="b9ecf-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ecf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9ecf-114">See Also</span></span>  
 [<span data-ttu-id="b9ecf-115">验证码</span><span class="sxs-lookup"><span data-stu-id="b9ecf-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
