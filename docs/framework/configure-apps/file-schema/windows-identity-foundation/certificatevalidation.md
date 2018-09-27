---
title: '&lt;certificatevalidation 设置&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 29881be43f02d275ad135efd97dc8b25a7409beb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47235450"
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="501c4-102">&lt;certificatevalidation 设置&gt;</span><span class="sxs-lookup"><span data-stu-id="501c4-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="501c4-103">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="501c4-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="501c4-104">如果特定的处理程序配置了其自己的验证程序，则将重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="501c4-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="501c4-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="501c4-105">\<system.identityModel></span></span>  
<span data-ttu-id="501c4-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="501c4-106">\<identityConfiguration></span></span>  
<span data-ttu-id="501c4-107">\<certificatevalidation 设置 ></span><span class="sxs-lookup"><span data-stu-id="501c4-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="501c4-108">语法</span><span class="sxs-lookup"><span data-stu-id="501c4-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="501c4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="501c4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="501c4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="501c4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="501c4-111">特性</span><span class="sxs-lookup"><span data-stu-id="501c4-111">Attributes</span></span>  
  
|<span data-ttu-id="501c4-112">特性</span><span class="sxs-lookup"><span data-stu-id="501c4-112">Attribute</span></span>|<span data-ttu-id="501c4-113">描述</span><span class="sxs-lookup"><span data-stu-id="501c4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="501c4-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="501c4-114">certificateValidationMode</span></span>|<span data-ttu-id="501c4-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="501c4-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="501c4-116">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="501c4-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="501c4-117">若要指定自定义验证程序，此特性设置为"Custom"并指定使用的验证程序[ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)元素。</span><span class="sxs-lookup"><span data-stu-id="501c4-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="501c4-118">可选。</span><span class="sxs-lookup"><span data-stu-id="501c4-118">Optional.</span></span>|  
|<span data-ttu-id="501c4-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="501c4-119">revocationMode</span></span>|<span data-ttu-id="501c4-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="501c4-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="501c4-121">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="501c4-121">The default value is "Online".</span></span> <span data-ttu-id="501c4-122">可选。</span><span class="sxs-lookup"><span data-stu-id="501c4-122">Optional.</span></span>|  
|<span data-ttu-id="501c4-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="501c4-123">trustedStoreLocation</span></span>|<span data-ttu-id="501c4-124">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="501c4-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="501c4-125">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="501c4-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="501c4-126">可选。</span><span class="sxs-lookup"><span data-stu-id="501c4-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="501c4-127">子元素</span><span class="sxs-lookup"><span data-stu-id="501c4-127">Child Elements</span></span>  
  
|<span data-ttu-id="501c4-128">元素</span><span class="sxs-lookup"><span data-stu-id="501c4-128">Element</span></span>|<span data-ttu-id="501c4-129">描述</span><span class="sxs-lookup"><span data-stu-id="501c4-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="501c4-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="501c4-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="501c4-131">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="501c4-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="501c4-132">仅当使用此类型`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"自定义"。</span><span class="sxs-lookup"><span data-stu-id="501c4-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="501c4-133">父元素</span><span class="sxs-lookup"><span data-stu-id="501c4-133">Parent Elements</span></span>  
  
|<span data-ttu-id="501c4-134">元素</span><span class="sxs-lookup"><span data-stu-id="501c4-134">Element</span></span>|<span data-ttu-id="501c4-135">描述</span><span class="sxs-lookup"><span data-stu-id="501c4-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="501c4-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="501c4-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="501c4-137">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="501c4-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="501c4-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="501c4-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="501c4-139">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="501c4-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="501c4-140">备注</span><span class="sxs-lookup"><span data-stu-id="501c4-140">Remarks</span></span>  
 <span data-ttu-id="501c4-141">一个`<certificateValidation>`可以在服务级别下指定元素`<identityConfiguration>`元素下的安全令牌处理程序集合级别上或`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="501c4-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="501c4-142">标记处理程序集合上的设置将覆盖在服务上指定的。</span><span class="sxs-lookup"><span data-stu-id="501c4-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="501c4-143">一些令牌处理程序，可在配置中指定的证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="501c4-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="501c4-144">在服务级别和对安全令牌处理程序集合上单个令牌处理程序设置将覆盖指定的维数。</span><span class="sxs-lookup"><span data-stu-id="501c4-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="501c4-145">示例</span><span class="sxs-lookup"><span data-stu-id="501c4-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
