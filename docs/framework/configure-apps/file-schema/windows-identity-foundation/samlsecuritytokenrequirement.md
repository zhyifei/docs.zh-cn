---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942494"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="a225c-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="a225c-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="a225c-102">为<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 、类或其中任何一个类的派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="a225c-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="a225c-103">由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类表示。</span><span class="sxs-lookup"><span data-stu-id="a225c-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="a225c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a225c-104">\<system.identityModel></span></span>  
<span data-ttu-id="a225c-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a225c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a225c-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a225c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a225c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a225c-107">\<add></span></span>  
<span data-ttu-id="a225c-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="a225c-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a225c-109">语法</span><span class="sxs-lookup"><span data-stu-id="a225c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a225c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a225c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a225c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a225c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a225c-112">特性</span><span class="sxs-lookup"><span data-stu-id="a225c-112">Attributes</span></span>  
  
|<span data-ttu-id="a225c-113">特性</span><span class="sxs-lookup"><span data-stu-id="a225c-113">Attribute</span></span>|<span data-ttu-id="a225c-114">描述</span><span class="sxs-lookup"><span data-stu-id="a225c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a225c-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="a225c-115">mapToWindows</span></span>|<span data-ttu-id="a225c-116">指定令牌处理程序是否应使用传入 UPN 声明将验证令牌映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="a225c-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="a225c-117">默认值为 "false"。</span><span class="sxs-lookup"><span data-stu-id="a225c-117">The default is "false".</span></span>|  
|<span data-ttu-id="a225c-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="a225c-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="a225c-119">一个<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值, 该值指定要用于 x.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="a225c-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a225c-120">默认值为 "Online"。</span><span class="sxs-lookup"><span data-stu-id="a225c-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="a225c-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a225c-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="a225c-122">一个<xref:System.ServiceModel.Security.X509CertificateValidationMode>值, 该值指定要用于 x.509 证书的验证模式。</span><span class="sxs-lookup"><span data-stu-id="a225c-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a225c-123">默认值为 "PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="a225c-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="a225c-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a225c-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="a225c-125">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值, 该值指定 x.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a225c-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="a225c-126">默认值为 "LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="a225c-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="a225c-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="a225c-127">issuerCertificateValidator</span></span>|<span data-ttu-id="a225c-128">派生自的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="a225c-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="a225c-129">如果该`issuerCertificateValidationMode`属性为 "Custom", 则此类型的实例将用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="a225c-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a225c-130">子元素</span><span class="sxs-lookup"><span data-stu-id="a225c-130">Child Elements</span></span>  
  
|<span data-ttu-id="a225c-131">元素</span><span class="sxs-lookup"><span data-stu-id="a225c-131">Element</span></span>|<span data-ttu-id="a225c-132">描述</span><span class="sxs-lookup"><span data-stu-id="a225c-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a225c-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="a225c-133">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="a225c-134">设置指定<xref:System.Security.Principal.IIdentity.Name%2A>属性的声明类型。</span><span class="sxs-lookup"><span data-stu-id="a225c-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="a225c-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="a225c-135">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="a225c-136">指定声明类型, 该声明类型定义<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>由标记处理程序的方法返回的对象集合中的角色类型声明。</span><span class="sxs-lookup"><span data-stu-id="a225c-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a225c-137">父元素</span><span class="sxs-lookup"><span data-stu-id="a225c-137">Parent Elements</span></span>  
  
|<span data-ttu-id="a225c-138">元素</span><span class="sxs-lookup"><span data-stu-id="a225c-138">Element</span></span>|<span data-ttu-id="a225c-139">描述</span><span class="sxs-lookup"><span data-stu-id="a225c-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a225c-140">\<add></span><span class="sxs-lookup"><span data-stu-id="a225c-140">\<add></span></span>](add.md)|<span data-ttu-id="a225c-141">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="a225c-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a225c-142">备注</span><span class="sxs-lookup"><span data-stu-id="a225c-142">Remarks</span></span>  
 <span data-ttu-id="a225c-143">`SamlSecurityTokenRequirement` <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>元素由对象模型中的<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类表示, 用于在或上配置属性。 `<samlSecurityTokenRequirement>`</span><span class="sxs-lookup"><span data-stu-id="a225c-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a225c-144">示例</span><span class="sxs-lookup"><span data-stu-id="a225c-144">Example</span></span>  
  
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
