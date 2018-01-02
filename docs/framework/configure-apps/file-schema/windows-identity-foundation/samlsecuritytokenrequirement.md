---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: a642a79618329a55afa98dba04e4ac5f419cae7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="69de5-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="69de5-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="69de5-103">提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。</span><span class="sxs-lookup"><span data-stu-id="69de5-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="69de5-104">由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类。</span><span class="sxs-lookup"><span data-stu-id="69de5-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="69de5-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="69de5-105">\<system.identityModel></span></span>  
<span data-ttu-id="69de5-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="69de5-106">\<identityConfiguration></span></span>  
<span data-ttu-id="69de5-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="69de5-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="69de5-108">\<add></span><span class="sxs-lookup"><span data-stu-id="69de5-108">\<add></span></span>  
<span data-ttu-id="69de5-109">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="69de5-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69de5-110">语法</span><span class="sxs-lookup"><span data-stu-id="69de5-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69de5-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="69de5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="69de5-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="69de5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69de5-113">特性</span><span class="sxs-lookup"><span data-stu-id="69de5-113">Attributes</span></span>  
  
|<span data-ttu-id="69de5-114">特性</span><span class="sxs-lookup"><span data-stu-id="69de5-114">Attribute</span></span>|<span data-ttu-id="69de5-115">描述</span><span class="sxs-lookup"><span data-stu-id="69de5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69de5-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="69de5-116">mapToWindows</span></span>|<span data-ttu-id="69de5-117">指定令牌处理程序是否应通过使用传入的 UPN 声明到 Windows 帐户映射验证令牌。</span><span class="sxs-lookup"><span data-stu-id="69de5-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="69de5-118">默认值为"false"。</span><span class="sxs-lookup"><span data-stu-id="69de5-118">The default is "false".</span></span>|  
|<span data-ttu-id="69de5-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="69de5-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="69de5-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="69de5-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="69de5-121">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="69de5-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="69de5-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="69de5-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="69de5-123"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="69de5-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="69de5-124">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="69de5-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="69de5-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="69de5-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="69de5-126">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="69de5-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="69de5-127">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="69de5-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="69de5-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="69de5-128">issuerCertificateValidator</span></span>|<span data-ttu-id="69de5-129">派生自的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="69de5-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="69de5-130">如果`issuerCertificateValidationMode`属性为"Custom"，此类型的实例将使用颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="69de5-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69de5-131">子元素</span><span class="sxs-lookup"><span data-stu-id="69de5-131">Child Elements</span></span>  
  
|<span data-ttu-id="69de5-132">元素</span><span class="sxs-lookup"><span data-stu-id="69de5-132">Element</span></span>|<span data-ttu-id="69de5-133">描述</span><span class="sxs-lookup"><span data-stu-id="69de5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69de5-134">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="69de5-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="69de5-135">设置指定的声明类型<xref:System.Security.Principal.IIdentity.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="69de5-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="69de5-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="69de5-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="69de5-137">指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="69de5-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69de5-138">父元素</span><span class="sxs-lookup"><span data-stu-id="69de5-138">Parent Elements</span></span>  
  
|<span data-ttu-id="69de5-139">元素</span><span class="sxs-lookup"><span data-stu-id="69de5-139">Element</span></span>|<span data-ttu-id="69de5-140">描述</span><span class="sxs-lookup"><span data-stu-id="69de5-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69de5-141">\<add></span><span class="sxs-lookup"><span data-stu-id="69de5-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="69de5-142">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="69de5-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69de5-143">备注</span><span class="sxs-lookup"><span data-stu-id="69de5-143">Remarks</span></span>  
 <span data-ttu-id="69de5-144">`<samlSecurityTokenRequirement>`元素表示由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类中的对象模型，并用于配置`SamlSecurityTokenRequirement`属性<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="69de5-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69de5-145">示例</span><span class="sxs-lookup"><span data-stu-id="69de5-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
