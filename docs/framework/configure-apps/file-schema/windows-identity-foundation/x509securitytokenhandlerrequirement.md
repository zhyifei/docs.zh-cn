---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251695"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="63ee0-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="63ee0-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="63ee0-102">提供<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生类的可选配置。</span><span class="sxs-lookup"><span data-stu-id="63ee0-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="63ee0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63ee0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63ee0-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="63ee0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="63ee0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="63ee0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="63ee0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="63ee0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="63ee0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="63ee0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="63ee0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<x509SecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="63ee0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ee0-109">语法</span><span class="sxs-lookup"><span data-stu-id="63ee0-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63ee0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63ee0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="63ee0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63ee0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63ee0-112">特性</span><span class="sxs-lookup"><span data-stu-id="63ee0-112">Attributes</span></span>  
  
|<span data-ttu-id="63ee0-113">特性</span><span class="sxs-lookup"><span data-stu-id="63ee0-113">Attribute</span></span>|<span data-ttu-id="63ee0-114">描述</span><span class="sxs-lookup"><span data-stu-id="63ee0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63ee0-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="63ee0-115">certificateValidationMode</span></span>|<span data-ttu-id="63ee0-116">一个<xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要用于 x.509 证书的验证模式。</span><span class="sxs-lookup"><span data-stu-id="63ee0-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="63ee0-117">默认值为 "PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="63ee0-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="63ee0-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="63ee0-118">mapToWindows</span></span>|<span data-ttu-id="63ee0-119">指定令牌处理程序是否应使用传入 UPN 声明将验证令牌映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="63ee0-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="63ee0-120">默认值为 "false"。</span><span class="sxs-lookup"><span data-stu-id="63ee0-120">The default is "false".</span></span>|  
|<span data-ttu-id="63ee0-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="63ee0-121">revocationMode</span></span>|<span data-ttu-id="63ee0-122">一个<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要用于 x.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="63ee0-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="63ee0-123">默认值为 "Online"。</span><span class="sxs-lookup"><span data-stu-id="63ee0-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="63ee0-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="63ee0-124">trustedStoreLocation</span></span>|<span data-ttu-id="63ee0-125">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 x.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="63ee0-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="63ee0-126">默认值为 "LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="63ee0-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="63ee0-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="63ee0-127">certificateValidator</span></span>|<span data-ttu-id="63ee0-128">派生自的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="63ee0-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="63ee0-129">如果该`certificateValidationMode`属性为 "Custom"，则此类型的实例将用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="63ee0-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63ee0-130">子元素</span><span class="sxs-lookup"><span data-stu-id="63ee0-130">Child Elements</span></span>  
 <span data-ttu-id="63ee0-131">无</span><span class="sxs-lookup"><span data-stu-id="63ee0-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63ee0-132">父元素</span><span class="sxs-lookup"><span data-stu-id="63ee0-132">Parent Elements</span></span>  
  
|<span data-ttu-id="63ee0-133">元素</span><span class="sxs-lookup"><span data-stu-id="63ee0-133">Element</span></span>|<span data-ttu-id="63ee0-134">描述</span><span class="sxs-lookup"><span data-stu-id="63ee0-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63ee0-135">\<add></span><span class="sxs-lookup"><span data-stu-id="63ee0-135">\<add></span></span>](add.md)|<span data-ttu-id="63ee0-136">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="63ee0-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="63ee0-137">示例</span><span class="sxs-lookup"><span data-stu-id="63ee0-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
