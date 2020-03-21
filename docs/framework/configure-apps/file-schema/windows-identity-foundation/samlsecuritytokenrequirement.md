---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152627"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="87a7d-101">\<samlSecurityToken 要求></span><span class="sxs-lookup"><span data-stu-id="87a7d-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="87a7d-102">为这些<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类之一的<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类、类或派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="87a7d-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="87a7d-103">由类<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>表示。</span><span class="sxs-lookup"><span data-stu-id="87a7d-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="87a7d-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87a7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87a7d-105">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="87a7d-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="87a7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="87a7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="87a7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="87a7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="87a7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="87a7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="87a7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityToken 要求>**</span><span class="sxs-lookup"><span data-stu-id="87a7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a7d-110">语法</span><span class="sxs-lookup"><span data-stu-id="87a7d-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87a7d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="87a7d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="87a7d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="87a7d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87a7d-113">属性</span><span class="sxs-lookup"><span data-stu-id="87a7d-113">Attributes</span></span>  
  
|<span data-ttu-id="87a7d-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="87a7d-114">Attribute</span></span>|<span data-ttu-id="87a7d-115">说明</span><span class="sxs-lookup"><span data-stu-id="87a7d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87a7d-116">地图到窗口</span><span class="sxs-lookup"><span data-stu-id="87a7d-116">mapToWindows</span></span>|<span data-ttu-id="87a7d-117">指定令牌处理程序是否应通过使用传入的 UPN 声明将验证令牌映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="87a7d-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="87a7d-118">默认值为“false”。</span><span class="sxs-lookup"><span data-stu-id="87a7d-118">The default is "false".</span></span>|  
|<span data-ttu-id="87a7d-119">颁发者证书重新调用模式</span><span class="sxs-lookup"><span data-stu-id="87a7d-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="87a7d-120">指定<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>要用于 X.509 证书的吊销模式的值。</span><span class="sxs-lookup"><span data-stu-id="87a7d-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="87a7d-121">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="87a7d-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="87a7d-122">颁发者验证模式</span><span class="sxs-lookup"><span data-stu-id="87a7d-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="87a7d-123">指定<xref:System.ServiceModel.Security.X509CertificateValidationMode>要用于 X.509 证书的验证模式的值。</span><span class="sxs-lookup"><span data-stu-id="87a7d-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="87a7d-124">默认值为"对等或链信任"。</span><span class="sxs-lookup"><span data-stu-id="87a7d-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="87a7d-125">颁发者证书信任存储位置</span><span class="sxs-lookup"><span data-stu-id="87a7d-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="87a7d-126">指定<xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 证书存储的值。</span><span class="sxs-lookup"><span data-stu-id="87a7d-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="87a7d-127">默认值为"本地计算机"。</span><span class="sxs-lookup"><span data-stu-id="87a7d-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="87a7d-128">颁发者证书验证器</span><span class="sxs-lookup"><span data-stu-id="87a7d-128">issuerCertificateValidator</span></span>|<span data-ttu-id="87a7d-129">派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="87a7d-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="87a7d-130">如果`issuerCertificateValidationMode`属性为"自定义"，则此类型的实例用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="87a7d-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87a7d-131">子元素</span><span class="sxs-lookup"><span data-stu-id="87a7d-131">Child Elements</span></span>  
  
|<span data-ttu-id="87a7d-132">元素</span><span class="sxs-lookup"><span data-stu-id="87a7d-132">Element</span></span>|<span data-ttu-id="87a7d-133">说明</span><span class="sxs-lookup"><span data-stu-id="87a7d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87a7d-134">\<名称 claimtype></span><span class="sxs-lookup"><span data-stu-id="87a7d-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="87a7d-135">设置指定<xref:System.Security.Principal.IIdentity.Name%2A>属性的声明类型。</span><span class="sxs-lookup"><span data-stu-id="87a7d-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="87a7d-136">\<角色声明类型></span><span class="sxs-lookup"><span data-stu-id="87a7d-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="87a7d-137">指定定义令牌处理程序<xref:System.Security.Claims.ClaimsIdentity><xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>方法返回的对象集合中的角色类型声明的声明类型。</span><span class="sxs-lookup"><span data-stu-id="87a7d-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87a7d-138">父元素</span><span class="sxs-lookup"><span data-stu-id="87a7d-138">Parent Elements</span></span>  
  
|<span data-ttu-id="87a7d-139">元素</span><span class="sxs-lookup"><span data-stu-id="87a7d-139">Element</span></span>|<span data-ttu-id="87a7d-140">说明</span><span class="sxs-lookup"><span data-stu-id="87a7d-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87a7d-141">\<添加></span><span class="sxs-lookup"><span data-stu-id="87a7d-141">\<add></span></span>](add.md)|<span data-ttu-id="87a7d-142">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="87a7d-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87a7d-143">备注</span><span class="sxs-lookup"><span data-stu-id="87a7d-143">Remarks</span></span>  
 <span data-ttu-id="87a7d-144">元素`<samlSecurityTokenRequirement>`由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象模型中的类表示，用于在`SamlSecurityTokenRequirement`<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>或 上配置属性。 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="87a7d-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a7d-145">示例</span><span class="sxs-lookup"><span data-stu-id="87a7d-145">Example</span></span>  
  
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
