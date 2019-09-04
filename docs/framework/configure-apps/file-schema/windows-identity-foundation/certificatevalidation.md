---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252137"
---
# <a name="certificatevalidation"></a><span data-ttu-id="69780-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="69780-101">\<certificateValidation></span></span>
<span data-ttu-id="69780-102">控制标记处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="69780-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="69780-103">如果为特定处理程序配置了其自己的验证程序，则会重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="69780-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="69780-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69780-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69780-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="69780-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="69780-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="69780-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="69780-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateValidation >**</span><span class="sxs-lookup"><span data-stu-id="69780-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69780-108">语法</span><span class="sxs-lookup"><span data-stu-id="69780-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69780-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="69780-109">Attributes and Elements</span></span>  
 <span data-ttu-id="69780-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="69780-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69780-111">特性</span><span class="sxs-lookup"><span data-stu-id="69780-111">Attributes</span></span>  
  
|<span data-ttu-id="69780-112">特性</span><span class="sxs-lookup"><span data-stu-id="69780-112">Attribute</span></span>|<span data-ttu-id="69780-113">描述</span><span class="sxs-lookup"><span data-stu-id="69780-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69780-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="69780-114">certificateValidationMode</span></span>|<span data-ttu-id="69780-115">一个<xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要用于 x.509 证书的验证模式。</span><span class="sxs-lookup"><span data-stu-id="69780-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="69780-116">默认值为 "PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="69780-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="69780-117">若要指定自定义验证程序，请将此属性设置为 "custom"，并使用[ \<certificateValidator >](certificatevalidator.md)元素指定验证程序。</span><span class="sxs-lookup"><span data-stu-id="69780-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="69780-118">可选。</span><span class="sxs-lookup"><span data-stu-id="69780-118">Optional.</span></span>|  
|<span data-ttu-id="69780-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="69780-119">revocationMode</span></span>|<span data-ttu-id="69780-120">一个<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要用于 x.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="69780-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="69780-121">默认值为 "Online"。</span><span class="sxs-lookup"><span data-stu-id="69780-121">The default value is "Online".</span></span> <span data-ttu-id="69780-122">可选。</span><span class="sxs-lookup"><span data-stu-id="69780-122">Optional.</span></span>|  
|<span data-ttu-id="69780-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="69780-123">trustedStoreLocation</span></span>|<span data-ttu-id="69780-124">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 x.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="69780-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="69780-125">默认值为 "LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="69780-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="69780-126">可选。</span><span class="sxs-lookup"><span data-stu-id="69780-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69780-127">子元素</span><span class="sxs-lookup"><span data-stu-id="69780-127">Child Elements</span></span>  
  
|<span data-ttu-id="69780-128">元素</span><span class="sxs-lookup"><span data-stu-id="69780-128">Element</span></span>|<span data-ttu-id="69780-129">描述</span><span class="sxs-lookup"><span data-stu-id="69780-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69780-130">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="69780-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="69780-131">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="69780-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="69780-132">仅当`certificateValidationMode` [ \<certificateValidation >](certificatevalidation.md)元素的属性设置为 "Custom" 时才使用此类型。</span><span class="sxs-lookup"><span data-stu-id="69780-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69780-133">父元素</span><span class="sxs-lookup"><span data-stu-id="69780-133">Parent Elements</span></span>  
  
|<span data-ttu-id="69780-134">元素</span><span class="sxs-lookup"><span data-stu-id="69780-134">Element</span></span>|<span data-ttu-id="69780-135">描述</span><span class="sxs-lookup"><span data-stu-id="69780-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69780-136">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="69780-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="69780-137">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="69780-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="69780-138">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="69780-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="69780-139">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="69780-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69780-140">备注</span><span class="sxs-lookup"><span data-stu-id="69780-140">Remarks</span></span>  
 <span data-ttu-id="69780-141">可以在元素`<identityConfiguration>`下的服务级别指定元素，或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="69780-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="69780-142">标记处理程序集合上的设置将重写服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="69780-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="69780-143">某些标记处理程序允许您在配置中指定证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="69780-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="69780-144">各个标记处理程序上的设置将覆盖在服务级别和安全令牌处理程序集合上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="69780-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69780-145">示例</span><span class="sxs-lookup"><span data-stu-id="69780-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
