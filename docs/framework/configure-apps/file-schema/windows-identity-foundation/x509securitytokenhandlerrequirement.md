---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152445"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="758c4-101">\<x509 安全令牌处理程序要求></span><span class="sxs-lookup"><span data-stu-id="758c4-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="758c4-102">为<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生类提供可选配置。</span><span class="sxs-lookup"><span data-stu-id="758c4-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="758c4-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="758c4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="758c4-104">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="758c4-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="758c4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="758c4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="758c4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="758c4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="758c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="758c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="758c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509 安全令牌处理程序要求>**</span><span class="sxs-lookup"><span data-stu-id="758c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758c4-109">语法</span><span class="sxs-lookup"><span data-stu-id="758c4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="758c4-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="758c4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="758c4-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="758c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="758c4-112">属性</span><span class="sxs-lookup"><span data-stu-id="758c4-112">Attributes</span></span>  
  
|<span data-ttu-id="758c4-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="758c4-113">Attribute</span></span>|<span data-ttu-id="758c4-114">说明</span><span class="sxs-lookup"><span data-stu-id="758c4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="758c4-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="758c4-115">certificateValidationMode</span></span>|<span data-ttu-id="758c4-116">指定<xref:System.ServiceModel.Security.X509CertificateValidationMode>要用于 X.509 证书的验证模式的值。</span><span class="sxs-lookup"><span data-stu-id="758c4-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="758c4-117">默认值为"对等或链信任"。</span><span class="sxs-lookup"><span data-stu-id="758c4-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="758c4-118">地图到窗口</span><span class="sxs-lookup"><span data-stu-id="758c4-118">mapToWindows</span></span>|<span data-ttu-id="758c4-119">指定令牌处理程序是否应通过使用传入的 UPN 声明将验证令牌映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="758c4-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="758c4-120">默认值为“false”。</span><span class="sxs-lookup"><span data-stu-id="758c4-120">The default is "false".</span></span>|  
|<span data-ttu-id="758c4-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="758c4-121">revocationMode</span></span>|<span data-ttu-id="758c4-122">指定<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>要用于 X.509 证书的吊销模式的值。</span><span class="sxs-lookup"><span data-stu-id="758c4-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="758c4-123">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="758c4-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="758c4-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="758c4-124">trustedStoreLocation</span></span>|<span data-ttu-id="758c4-125">指定<xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 证书存储的值。</span><span class="sxs-lookup"><span data-stu-id="758c4-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="758c4-126">默认值为"本地计算机"。</span><span class="sxs-lookup"><span data-stu-id="758c4-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="758c4-127">证书验证器</span><span class="sxs-lookup"><span data-stu-id="758c4-127">certificateValidator</span></span>|<span data-ttu-id="758c4-128">派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="758c4-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="758c4-129">如果`certificateValidationMode`属性为"自定义"，则此类型的实例用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="758c4-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="758c4-130">子元素</span><span class="sxs-lookup"><span data-stu-id="758c4-130">Child Elements</span></span>  
 <span data-ttu-id="758c4-131">无</span><span class="sxs-lookup"><span data-stu-id="758c4-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="758c4-132">父元素</span><span class="sxs-lookup"><span data-stu-id="758c4-132">Parent Elements</span></span>  
  
|<span data-ttu-id="758c4-133">元素</span><span class="sxs-lookup"><span data-stu-id="758c4-133">Element</span></span>|<span data-ttu-id="758c4-134">说明</span><span class="sxs-lookup"><span data-stu-id="758c4-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="758c4-135">\<添加></span><span class="sxs-lookup"><span data-stu-id="758c4-135">\<add></span></span>](add.md)|<span data-ttu-id="758c4-136">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="758c4-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="758c4-137">示例</span><span class="sxs-lookup"><span data-stu-id="758c4-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
