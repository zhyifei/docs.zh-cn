---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667348"
---
# <a name="certificatevalidation"></a><span data-ttu-id="6adfe-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6adfe-101">\<certificateValidation></span></span>
<span data-ttu-id="6adfe-102">控制令牌处理程序用来验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="6adfe-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6adfe-103">如果特定的处理程序配置了其自己的验证程序，则将重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="6adfe-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="6adfe-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6adfe-104">\<system.identityModel></span></span>  
<span data-ttu-id="6adfe-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6adfe-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6adfe-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6adfe-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adfe-107">语法</span><span class="sxs-lookup"><span data-stu-id="6adfe-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6adfe-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6adfe-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6adfe-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6adfe-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6adfe-110">特性</span><span class="sxs-lookup"><span data-stu-id="6adfe-110">Attributes</span></span>  
  
|<span data-ttu-id="6adfe-111">特性</span><span class="sxs-lookup"><span data-stu-id="6adfe-111">Attribute</span></span>|<span data-ttu-id="6adfe-112">描述</span><span class="sxs-lookup"><span data-stu-id="6adfe-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6adfe-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6adfe-113">certificateValidationMode</span></span>|<span data-ttu-id="6adfe-114"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="6adfe-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6adfe-115">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="6adfe-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="6adfe-116">若要指定自定义验证程序，此特性设置为"Custom"并指定使用的验证程序[ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)元素。</span><span class="sxs-lookup"><span data-stu-id="6adfe-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="6adfe-117">可选。</span><span class="sxs-lookup"><span data-stu-id="6adfe-117">Optional.</span></span>|  
|<span data-ttu-id="6adfe-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="6adfe-118">revocationMode</span></span>|<span data-ttu-id="6adfe-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="6adfe-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6adfe-120">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="6adfe-120">The default value is "Online".</span></span> <span data-ttu-id="6adfe-121">可选。</span><span class="sxs-lookup"><span data-stu-id="6adfe-121">Optional.</span></span>|  
|<span data-ttu-id="6adfe-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6adfe-122">trustedStoreLocation</span></span>|<span data-ttu-id="6adfe-123">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="6adfe-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="6adfe-124">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="6adfe-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="6adfe-125">可选。</span><span class="sxs-lookup"><span data-stu-id="6adfe-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6adfe-126">子元素</span><span class="sxs-lookup"><span data-stu-id="6adfe-126">Child Elements</span></span>  
  
|<span data-ttu-id="6adfe-127">元素</span><span class="sxs-lookup"><span data-stu-id="6adfe-127">Element</span></span>|<span data-ttu-id="6adfe-128">描述</span><span class="sxs-lookup"><span data-stu-id="6adfe-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6adfe-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="6adfe-129">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="6adfe-130">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="6adfe-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="6adfe-131">仅当使用此类型`certificateValidationMode`的属性[ \<certificatevalidation 设置 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"自定义"。</span><span class="sxs-lookup"><span data-stu-id="6adfe-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6adfe-132">父元素</span><span class="sxs-lookup"><span data-stu-id="6adfe-132">Parent Elements</span></span>  
  
|<span data-ttu-id="6adfe-133">元素</span><span class="sxs-lookup"><span data-stu-id="6adfe-133">Element</span></span>|<span data-ttu-id="6adfe-134">描述</span><span class="sxs-lookup"><span data-stu-id="6adfe-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6adfe-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6adfe-135">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="6adfe-136">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="6adfe-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="6adfe-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6adfe-137">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6adfe-138">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="6adfe-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6adfe-139">备注</span><span class="sxs-lookup"><span data-stu-id="6adfe-139">Remarks</span></span>  
 <span data-ttu-id="6adfe-140">一个`<certificateValidation>`可以在服务级别下指定元素`<identityConfiguration>`元素下的安全令牌处理程序集合级别上或`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="6adfe-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="6adfe-141">标记处理程序集合上的设置将覆盖在服务上指定的。</span><span class="sxs-lookup"><span data-stu-id="6adfe-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="6adfe-142">一些令牌处理程序，可在配置中指定的证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="6adfe-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="6adfe-143">在服务级别和对安全令牌处理程序集合上单个令牌处理程序设置将覆盖指定的维数。</span><span class="sxs-lookup"><span data-stu-id="6adfe-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6adfe-144">示例</span><span class="sxs-lookup"><span data-stu-id="6adfe-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
