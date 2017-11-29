---
title: "Authenticode（非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e90a13ebf46f1891061c78435b7ba47d68de001d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="98617-102">Authenticode（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="98617-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="98617-103">支持验证码 XrML 许可证创建和验证模块。</span><span class="sxs-lookup"><span data-stu-id="98617-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98617-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="98617-104">In This Section</span></span>  
 [<span data-ttu-id="98617-105">_AxlGetIssuerPublicKeyHash 函数</span><span class="sxs-lookup"><span data-stu-id="98617-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="98617-106">检索与用于对指定证书进行签名的私钥关联的公钥的 SHA-1 哈希。</span><span class="sxs-lookup"><span data-stu-id="98617-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="98617-107">_AxlPublicKeyBlobToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="98617-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="98617-108">从 CSP PUBLICKEYBLOB 格式计算强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="98617-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="98617-109">_AxlRSAKeyValueToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="98617-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="98617-110">将模数和指数转换为强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="98617-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="98617-111">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="98617-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="98617-112">释放为 AXL_AUTHENTICODE_SIGNER_INFO 结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="98617-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="98617-113">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="98617-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="98617-114">释放为 AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="98617-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="98617-115">CertTimestampAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="98617-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="98617-116">为由 CertCreateAuthenticodeLicense 创建的验证码 XrML 许可证添加时间戳。</span><span class="sxs-lookup"><span data-stu-id="98617-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="98617-117">CertVerifyAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="98617-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="98617-118">验证验证码 XrML 许可证的有效性。</span><span class="sxs-lookup"><span data-stu-id="98617-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="98617-119">AXL_AUTHENTICODE_SIGNER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="98617-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="98617-120">定义验证码签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="98617-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="98617-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="98617-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="98617-122">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="98617-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98617-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98617-123">See Also</span></span>  
 [<span data-ttu-id="98617-124">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="98617-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
