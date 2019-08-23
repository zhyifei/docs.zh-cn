---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941911"
---
# <a name="certificatevalidation"></a><span data-ttu-id="ff417-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ff417-101">\<certificateValidation></span></span>
<span data-ttu-id="ff417-102">控制标记处理程序用于验证证书的设置。</span><span class="sxs-lookup"><span data-stu-id="ff417-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ff417-103">如果为特定处理程序配置了其自己的验证程序, 则会重写这些设置。</span><span class="sxs-lookup"><span data-stu-id="ff417-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="ff417-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ff417-104">\<system.identityModel></span></span>  
<span data-ttu-id="ff417-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff417-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ff417-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ff417-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff417-107">语法</span><span class="sxs-lookup"><span data-stu-id="ff417-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff417-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ff417-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ff417-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ff417-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff417-110">特性</span><span class="sxs-lookup"><span data-stu-id="ff417-110">Attributes</span></span>  
  
|<span data-ttu-id="ff417-111">特性</span><span class="sxs-lookup"><span data-stu-id="ff417-111">Attribute</span></span>|<span data-ttu-id="ff417-112">描述</span><span class="sxs-lookup"><span data-stu-id="ff417-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff417-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ff417-113">certificateValidationMode</span></span>|<span data-ttu-id="ff417-114">一个<xref:System.ServiceModel.Security.X509CertificateValidationMode>值, 该值指定要用于 x.509 证书的验证模式。</span><span class="sxs-lookup"><span data-stu-id="ff417-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ff417-115">默认值为 "PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="ff417-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="ff417-116">若要指定自定义验证程序, 请将此属性设置为 "custom", 并使用[ \<certificateValidator >](certificatevalidator.md)元素指定验证程序。</span><span class="sxs-lookup"><span data-stu-id="ff417-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="ff417-117">可选。</span><span class="sxs-lookup"><span data-stu-id="ff417-117">Optional.</span></span>|  
|<span data-ttu-id="ff417-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ff417-118">revocationMode</span></span>|<span data-ttu-id="ff417-119">一个<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值, 该值指定要用于 x.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="ff417-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ff417-120">默认值为 "Online"。</span><span class="sxs-lookup"><span data-stu-id="ff417-120">The default value is "Online".</span></span> <span data-ttu-id="ff417-121">可选。</span><span class="sxs-lookup"><span data-stu-id="ff417-121">Optional.</span></span>|  
|<span data-ttu-id="ff417-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ff417-122">trustedStoreLocation</span></span>|<span data-ttu-id="ff417-123">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值, 该值指定 x.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ff417-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ff417-124">默认值为 "LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="ff417-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="ff417-125">可选。</span><span class="sxs-lookup"><span data-stu-id="ff417-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff417-126">子元素</span><span class="sxs-lookup"><span data-stu-id="ff417-126">Child Elements</span></span>  
  
|<span data-ttu-id="ff417-127">元素</span><span class="sxs-lookup"><span data-stu-id="ff417-127">Element</span></span>|<span data-ttu-id="ff417-128">描述</span><span class="sxs-lookup"><span data-stu-id="ff417-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff417-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="ff417-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="ff417-130">指定证书验证的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="ff417-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ff417-131">仅当`certificateValidationMode` [ \<certificateValidation >](certificatevalidation.md)元素的属性设置为 "Custom" 时才使用此类型。</span><span class="sxs-lookup"><span data-stu-id="ff417-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff417-132">父元素</span><span class="sxs-lookup"><span data-stu-id="ff417-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ff417-133">元素</span><span class="sxs-lookup"><span data-stu-id="ff417-133">Element</span></span>|<span data-ttu-id="ff417-134">描述</span><span class="sxs-lookup"><span data-stu-id="ff417-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff417-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff417-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ff417-136">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="ff417-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ff417-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff417-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ff417-138">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="ff417-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff417-139">备注</span><span class="sxs-lookup"><span data-stu-id="ff417-139">Remarks</span></span>  
 <span data-ttu-id="ff417-140">可以在元素`<identityConfiguration>`下的服务级别指定元素, 或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="ff417-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ff417-141">标记处理程序集合上的设置将重写服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="ff417-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="ff417-142">某些标记处理程序允许您在配置中指定证书验证设置。</span><span class="sxs-lookup"><span data-stu-id="ff417-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="ff417-143">各个标记处理程序上的设置将覆盖在服务级别和安全令牌处理程序集合上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="ff417-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff417-144">示例</span><span class="sxs-lookup"><span data-stu-id="ff417-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
