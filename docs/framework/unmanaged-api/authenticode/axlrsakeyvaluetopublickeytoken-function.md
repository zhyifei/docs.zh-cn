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
ms.openlocfilehash: 1f53df33a65d3f75b7574eda3507e370c2e086ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099822"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="d0857-102">\_AxlRSAKeyValueToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="d0857-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="d0857-103">将模数和指数转换为强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d0857-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0857-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0857-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0857-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0857-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="d0857-106">中Base64 编码的模数 blob （来自 \<模数 > 元素）。</span><span class="sxs-lookup"><span data-stu-id="d0857-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="d0857-107">请参阅[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="d0857-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="d0857-108">中Base64 编码的指数 blob （来自 \<指数 > 元素）。</span><span class="sxs-lookup"><span data-stu-id="d0857-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="d0857-109">请参阅[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="d0857-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="d0857-110">[out] 指向 WCHAR \* 的指针，用于接收十六进制编码的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d0857-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0857-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d0857-111">Return Value</span></span>  
 <span data-ttu-id="d0857-112">如果此函数成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="d0857-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d0857-113">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="d0857-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0857-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0857-114">See also</span></span>

- [<span data-ttu-id="d0857-115">验证码</span><span class="sxs-lookup"><span data-stu-id="d0857-115">Authenticode</span></span>](index.md)
