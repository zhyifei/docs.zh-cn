---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af4dc459da49b46d70276d3f4bcd5f94d2a91ffe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="61f6b-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="61f6b-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="61f6b-103">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="61f6b-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="61f6b-104">如果使用自己的验证程序配置特定的处理程序，则将重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="61f6b-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="61f6b-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="61f6b-105">\<system.identityModel></span></span>  
<span data-ttu-id="61f6b-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="61f6b-106">\<identityConfiguration></span></span>  
<span data-ttu-id="61f6b-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="61f6b-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f6b-108">语法</span><span class="sxs-lookup"><span data-stu-id="61f6b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61f6b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="61f6b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="61f6b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="61f6b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61f6b-111">特性</span><span class="sxs-lookup"><span data-stu-id="61f6b-111">Attributes</span></span>  
  
|<span data-ttu-id="61f6b-112">特性</span><span class="sxs-lookup"><span data-stu-id="61f6b-112">Attribute</span></span>|<span data-ttu-id="61f6b-113">描述</span><span class="sxs-lookup"><span data-stu-id="61f6b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61f6b-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="61f6b-114">certificateValidationMode</span></span>|<span data-ttu-id="61f6b-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="61f6b-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="61f6b-116">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="61f6b-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="61f6b-117">若要指定自定义验证程序，此特性设置为"Custom"并指定使用的验证程序[ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)元素。</span><span class="sxs-lookup"><span data-stu-id="61f6b-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="61f6b-118">可选。</span><span class="sxs-lookup"><span data-stu-id="61f6b-118">Optional.</span></span>|  
|<span data-ttu-id="61f6b-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="61f6b-119">revocationMode</span></span>|<span data-ttu-id="61f6b-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="61f6b-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="61f6b-121">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="61f6b-121">The default value is "Online".</span></span> <span data-ttu-id="61f6b-122">可选。</span><span class="sxs-lookup"><span data-stu-id="61f6b-122">Optional.</span></span>|  
|<span data-ttu-id="61f6b-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="61f6b-123">trustedStoreLocation</span></span>|<span data-ttu-id="61f6b-124">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="61f6b-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="61f6b-125">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="61f6b-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="61f6b-126">可选。</span><span class="sxs-lookup"><span data-stu-id="61f6b-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61f6b-127">子元素</span><span class="sxs-lookup"><span data-stu-id="61f6b-127">Child Elements</span></span>  
  
|<span data-ttu-id="61f6b-128">元素</span><span class="sxs-lookup"><span data-stu-id="61f6b-128">Element</span></span>|<span data-ttu-id="61f6b-129">描述</span><span class="sxs-lookup"><span data-stu-id="61f6b-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61f6b-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="61f6b-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="61f6b-131">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="61f6b-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="61f6b-132">仅当使用此类型`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"Custom"。</span><span class="sxs-lookup"><span data-stu-id="61f6b-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61f6b-133">父元素</span><span class="sxs-lookup"><span data-stu-id="61f6b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="61f6b-134">元素</span><span class="sxs-lookup"><span data-stu-id="61f6b-134">Element</span></span>|<span data-ttu-id="61f6b-135">描述</span><span class="sxs-lookup"><span data-stu-id="61f6b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61f6b-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="61f6b-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="61f6b-137">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="61f6b-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="61f6b-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="61f6b-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="61f6b-139">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="61f6b-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61f6b-140">备注</span><span class="sxs-lookup"><span data-stu-id="61f6b-140">Remarks</span></span>  
 <span data-ttu-id="61f6b-141">A`<certificateValidation>`可以在服务级别下指定元素`<identityConfiguration>`元素或下位于安全令牌处理程序集合级别`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="61f6b-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="61f6b-142">令牌处理程序集合上的设置会覆盖在服务上指定。</span><span class="sxs-lookup"><span data-stu-id="61f6b-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="61f6b-143">某些令牌处理程序，可以在配置中指定证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="61f6b-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="61f6b-144">在服务级别和对安全令牌处理程序集合中，重写这些指定上各个标记处理程序的设置。</span><span class="sxs-lookup"><span data-stu-id="61f6b-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f6b-145">示例</span><span class="sxs-lookup"><span data-stu-id="61f6b-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
