---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: e1b8acd48ee185b3c6c50f70321bb9ca66e8e02b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284617"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="87ca9-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="87ca9-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="87ca9-102">提供用于配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类的任何一个的派生的类。</span><span class="sxs-lookup"><span data-stu-id="87ca9-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="87ca9-103">由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类。</span><span class="sxs-lookup"><span data-stu-id="87ca9-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="87ca9-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="87ca9-104">\<system.identityModel></span></span>  
<span data-ttu-id="87ca9-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="87ca9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="87ca9-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="87ca9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="87ca9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="87ca9-107">\<add></span></span>  
<span data-ttu-id="87ca9-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="87ca9-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87ca9-109">语法</span><span class="sxs-lookup"><span data-stu-id="87ca9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87ca9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="87ca9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="87ca9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="87ca9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87ca9-112">特性</span><span class="sxs-lookup"><span data-stu-id="87ca9-112">Attributes</span></span>  
  
|<span data-ttu-id="87ca9-113">特性</span><span class="sxs-lookup"><span data-stu-id="87ca9-113">Attribute</span></span>|<span data-ttu-id="87ca9-114">描述</span><span class="sxs-lookup"><span data-stu-id="87ca9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87ca9-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="87ca9-115">mapToWindows</span></span>|<span data-ttu-id="87ca9-116">指定的标记处理程序是否应使用传入 UPN 声明到 Windows 帐户映射验证令牌。</span><span class="sxs-lookup"><span data-stu-id="87ca9-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="87ca9-117">默认值为"false"。</span><span class="sxs-lookup"><span data-stu-id="87ca9-117">The default is "false".</span></span>|  
|<span data-ttu-id="87ca9-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="87ca9-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="87ca9-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="87ca9-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="87ca9-120">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="87ca9-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="87ca9-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="87ca9-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="87ca9-122"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="87ca9-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="87ca9-123">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="87ca9-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="87ca9-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="87ca9-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="87ca9-125">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="87ca9-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="87ca9-126">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="87ca9-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="87ca9-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="87ca9-127">issuerCertificateValidator</span></span>|<span data-ttu-id="87ca9-128">派生的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="87ca9-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="87ca9-129">如果`issuerCertificateValidationMode`属性为"自定义"，此类型的实例用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="87ca9-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87ca9-130">子元素</span><span class="sxs-lookup"><span data-stu-id="87ca9-130">Child Elements</span></span>  
  
|<span data-ttu-id="87ca9-131">元素</span><span class="sxs-lookup"><span data-stu-id="87ca9-131">Element</span></span>|<span data-ttu-id="87ca9-132">描述</span><span class="sxs-lookup"><span data-stu-id="87ca9-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87ca9-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="87ca9-133">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="87ca9-134">设置指定的声明类型<xref:System.Security.Principal.IIdentity.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="87ca9-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="87ca9-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="87ca9-135">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="87ca9-136">指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序的方法。</span><span class="sxs-lookup"><span data-stu-id="87ca9-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87ca9-137">父元素</span><span class="sxs-lookup"><span data-stu-id="87ca9-137">Parent Elements</span></span>  
  
|<span data-ttu-id="87ca9-138">元素</span><span class="sxs-lookup"><span data-stu-id="87ca9-138">Element</span></span>|<span data-ttu-id="87ca9-139">描述</span><span class="sxs-lookup"><span data-stu-id="87ca9-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87ca9-140">\<add></span><span class="sxs-lookup"><span data-stu-id="87ca9-140">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="87ca9-141">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="87ca9-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87ca9-142">备注</span><span class="sxs-lookup"><span data-stu-id="87ca9-142">Remarks</span></span>  
 <span data-ttu-id="87ca9-143">`<samlSecurityTokenRequirement>`元素表示由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类的对象模型中，并用于配置`SamlSecurityTokenRequirement`上的属性<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="87ca9-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87ca9-144">示例</span><span class="sxs-lookup"><span data-stu-id="87ca9-144">Example</span></span>  
  
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
