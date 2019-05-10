---
title: CertVerifyAuthenticodeLicense 函数
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06f69bf867b565edbab06dadb32e5377357e91f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617686"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="42e29-102">CertVerifyAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="42e29-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="42e29-103">验证验证码 XrML 许可证的有效性。</span><span class="sxs-lookup"><span data-stu-id="42e29-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e29-104">语法</span><span class="sxs-lookup"><span data-stu-id="42e29-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42e29-105">参数</span><span class="sxs-lookup"><span data-stu-id="42e29-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="42e29-106">[in] 要验证的验证码 XrML 许可证。</span><span class="sxs-lookup"><span data-stu-id="42e29-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="42e29-107">请参阅[CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob)结构。</span><span class="sxs-lookup"><span data-stu-id="42e29-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="42e29-108">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="42e29-108">[in] Optional.</span></span> <span data-ttu-id="42e29-109">以下值的组合：</span><span class="sxs-lookup"><span data-stu-id="42e29-109">A combination of following values:</span></span>  
  
- <span data-ttu-id="42e29-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="42e29-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
- <span data-ttu-id="42e29-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="42e29-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
- <span data-ttu-id="42e29-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="42e29-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
- <span data-ttu-id="42e29-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="42e29-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
- <span data-ttu-id="42e29-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="42e29-114">AXL_LIFETIME_SIGNING</span></span>  
  
- <span data-ttu-id="42e29-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="42e29-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="42e29-116">[out] 接收签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="42e29-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="42e29-117">如果许可证未进行签名，则 `dwError` 将设置为 TRUST_E_NOSIGNATURE。</span><span class="sxs-lookup"><span data-stu-id="42e29-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="42e29-118">它是调用方负责释放使用的资源[CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)函数之后，使用。</span><span class="sxs-lookup"><span data-stu-id="42e29-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="42e29-119">请参阅[AXL_AUTHENTICODE_SIGNER_INFO 结构](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="42e29-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="42e29-120">[out] 接收时间戳签署人的信息（如果有）。</span><span class="sxs-lookup"><span data-stu-id="42e29-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="42e29-121">如果未对许可证签署时间戳，则 `dwError` 将设置为 TRUST_E_NOSIGNATURE。</span><span class="sxs-lookup"><span data-stu-id="42e29-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="42e29-122">它是调用方负责释放使用的资源[CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)函数之后，使用。</span><span class="sxs-lookup"><span data-stu-id="42e29-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="42e29-123">请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="42e29-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42e29-124">返回值</span><span class="sxs-lookup"><span data-stu-id="42e29-124">Return Value</span></span>  
 <span data-ttu-id="42e29-125">如果成功，则返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="42e29-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="42e29-126">否则，返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="42e29-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e29-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="42e29-127">See also</span></span>

- [<span data-ttu-id="42e29-128">验证码</span><span class="sxs-lookup"><span data-stu-id="42e29-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [<span data-ttu-id="42e29-129">GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="42e29-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="42e29-130">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="42e29-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
