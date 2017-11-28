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
ms.openlocfilehash: e0d8d467c2636f5ce95cf5fed189ae00c3ca75fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="7c91b-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="7c91b-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="7c91b-103">提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。</span><span class="sxs-lookup"><span data-stu-id="7c91b-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="7c91b-104">由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类。</span><span class="sxs-lookup"><span data-stu-id="7c91b-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="7c91b-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="7c91b-105">\<system.identityModel></span></span>  
<span data-ttu-id="7c91b-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7c91b-106">\<identityConfiguration></span></span>  
<span data-ttu-id="7c91b-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="7c91b-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7c91b-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7c91b-108">\<add></span></span>  
<span data-ttu-id="7c91b-109">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="7c91b-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c91b-110">语法</span><span class="sxs-lookup"><span data-stu-id="7c91b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c91b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7c91b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7c91b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7c91b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c91b-113">特性</span><span class="sxs-lookup"><span data-stu-id="7c91b-113">Attributes</span></span>  
  
|<span data-ttu-id="7c91b-114">特性</span><span class="sxs-lookup"><span data-stu-id="7c91b-114">Attribute</span></span>|<span data-ttu-id="7c91b-115">描述</span><span class="sxs-lookup"><span data-stu-id="7c91b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c91b-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="7c91b-116">mapToWindows</span></span>|<span data-ttu-id="7c91b-117">指定令牌处理程序是否应通过使用传入的 UPN 声明到 Windows 帐户映射验证令牌。</span><span class="sxs-lookup"><span data-stu-id="7c91b-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="7c91b-118">默认值为"false"。</span><span class="sxs-lookup"><span data-stu-id="7c91b-118">The default is "false".</span></span>|  
|<span data-ttu-id="7c91b-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="7c91b-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="7c91b-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="7c91b-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="7c91b-121">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="7c91b-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="7c91b-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="7c91b-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="7c91b-123"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="7c91b-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="7c91b-124">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="7c91b-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="7c91b-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="7c91b-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="7c91b-126">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="7c91b-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="7c91b-127">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="7c91b-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="7c91b-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="7c91b-128">issuerCertificateValidator</span></span>|<span data-ttu-id="7c91b-129">派生自的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="7c91b-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="7c91b-130">如果`issuerCertificateValidationMode`属性为"Custom"，此类型的实例将使用颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="7c91b-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c91b-131">子元素</span><span class="sxs-lookup"><span data-stu-id="7c91b-131">Child Elements</span></span>  
  
|<span data-ttu-id="7c91b-132">元素</span><span class="sxs-lookup"><span data-stu-id="7c91b-132">Element</span></span>|<span data-ttu-id="7c91b-133">描述</span><span class="sxs-lookup"><span data-stu-id="7c91b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c91b-134">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="7c91b-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="7c91b-135">设置指定的声明类型<xref:System.Security.Principal.IIdentity.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7c91b-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="7c91b-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="7c91b-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="7c91b-137">指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="7c91b-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c91b-138">父元素</span><span class="sxs-lookup"><span data-stu-id="7c91b-138">Parent Elements</span></span>  
  
|<span data-ttu-id="7c91b-139">元素</span><span class="sxs-lookup"><span data-stu-id="7c91b-139">Element</span></span>|<span data-ttu-id="7c91b-140">说明</span><span class="sxs-lookup"><span data-stu-id="7c91b-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c91b-141">\<add></span><span class="sxs-lookup"><span data-stu-id="7c91b-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="7c91b-142">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="7c91b-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c91b-143">备注</span><span class="sxs-lookup"><span data-stu-id="7c91b-143">Remarks</span></span>  
 <span data-ttu-id="7c91b-144">`<samlSecurityTokenRequirement>`元素表示由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类中的对象模型，并用于配置`SamlSecurityTokenRequirement`属性<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="7c91b-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c91b-145">示例</span><span class="sxs-lookup"><span data-stu-id="7c91b-145">Example</span></span>  
  
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
