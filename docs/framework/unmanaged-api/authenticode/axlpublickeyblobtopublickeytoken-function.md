---
title: _AxlPublicKeyBlobToPublicKeyToken 函数
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ac147596794f748d3160cdbd34b9f306dfdb379
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604413"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="5a376-102">_AxlPublicKeyBlobToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="5a376-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="5a376-103">从 CSP PUBLICKEYBLOB 格式计算强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="5a376-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a376-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a376-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a376-105">参数</span><span class="sxs-lookup"><span data-stu-id="5a376-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="5a376-106">[in] CSP 公钥 Blob。</span><span class="sxs-lookup"><span data-stu-id="5a376-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="5a376-107">[out] 指向 WCHAR \* 的指针，用于接收十六进制编码的公钥哈希。</span><span class="sxs-lookup"><span data-stu-id="5a376-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a376-108">返回值</span><span class="sxs-lookup"><span data-stu-id="5a376-108">Return Value</span></span>  
 <span data-ttu-id="5a376-109">如果函数成功，则为 `S_OK`；否则为 `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="5a376-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a376-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a376-110">See also</span></span>
- [<span data-ttu-id="5a376-111">验证码</span><span class="sxs-lookup"><span data-stu-id="5a376-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
