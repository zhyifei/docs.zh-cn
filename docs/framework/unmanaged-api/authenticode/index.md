---
title: Authenticode（非托管 API 参考）
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 1b8b2222950c75f7f9d2ec2704f722087645cd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132456"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="8d3bc-102">Authenticode（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="8d3bc-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="8d3bc-103">支持验证码 XrML 许可证创建和验证模块。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d3bc-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d3bc-104">In This Section</span></span>  
 [<span data-ttu-id="8d3bc-105">_AxlGetIssuerPublicKeyHash 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="8d3bc-106">检索与用于对指定证书进行签名的私钥关联的公钥的 SHA-1 哈希。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="8d3bc-107">_AxlPublicKeyBlobToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="8d3bc-108">从 CSP PUBLICKEYBLOB 格式计算强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="8d3bc-109">_AxlRSAKeyValueToPublicKeyToken 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="8d3bc-110">将模数和指数转换为强名称公钥标记。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="8d3bc-111">CertFreeAuthenticodeSignerInfo 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="8d3bc-112">释放为 AXL_AUTHENTICODE_SIGNER_INFO 结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="8d3bc-113">CertFreeAuthenticodeTimestamperInfo 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="8d3bc-114">释放为 AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构分配的资源。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="8d3bc-115">CertTimestampAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="8d3bc-116">为由 CertCreateAuthenticodeLicense 创建的验证码 XrML 许可证添加时间戳。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="8d3bc-117">CertVerifyAuthenticodeLicense 函数</span><span class="sxs-lookup"><span data-stu-id="8d3bc-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="8d3bc-118">验证验证码 XrML 许可证的有效性。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="8d3bc-119">AXL_AUTHENTICODE_SIGNER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8d3bc-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="8d3bc-120">定义验证码签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="8d3bc-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8d3bc-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="8d3bc-122">定义验证码时间戳签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="8d3bc-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3bc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d3bc-123">See also</span></span>

- [<span data-ttu-id="8d3bc-124">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="8d3bc-124">Unmanaged API Reference</span></span>](../index.md)
