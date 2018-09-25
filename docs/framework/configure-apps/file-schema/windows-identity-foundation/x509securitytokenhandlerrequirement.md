---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 994677904cada71dbc7cce4b6ca0de1d4dc65014
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085631"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="250a8-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="250a8-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="250a8-103">提供的可选配置<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="250a8-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="250a8-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="250a8-104">\<system.identityModel></span></span>  
<span data-ttu-id="250a8-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="250a8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="250a8-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="250a8-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="250a8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="250a8-107">\<add></span></span>  
<span data-ttu-id="250a8-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="250a8-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="250a8-109">语法</span><span class="sxs-lookup"><span data-stu-id="250a8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="250a8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="250a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="250a8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="250a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="250a8-112">特性</span><span class="sxs-lookup"><span data-stu-id="250a8-112">Attributes</span></span>  
  
|<span data-ttu-id="250a8-113">特性</span><span class="sxs-lookup"><span data-stu-id="250a8-113">Attribute</span></span>|<span data-ttu-id="250a8-114">描述</span><span class="sxs-lookup"><span data-stu-id="250a8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="250a8-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="250a8-115">certificateValidationMode</span></span>|<span data-ttu-id="250a8-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="250a8-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="250a8-117">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="250a8-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="250a8-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="250a8-118">mapToWindows</span></span>|<span data-ttu-id="250a8-119">指定的标记处理程序是否应使用传入 UPN 声明到 Windows 帐户映射验证令牌。</span><span class="sxs-lookup"><span data-stu-id="250a8-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="250a8-120">默认值为"false"。</span><span class="sxs-lookup"><span data-stu-id="250a8-120">The default is "false".</span></span>|  
|<span data-ttu-id="250a8-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="250a8-121">revocationMode</span></span>|<span data-ttu-id="250a8-122"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="250a8-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="250a8-123">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="250a8-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="250a8-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="250a8-124">trustedStoreLocation</span></span>|<span data-ttu-id="250a8-125">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="250a8-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="250a8-126">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="250a8-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="250a8-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="250a8-127">certificateValidator</span></span>|<span data-ttu-id="250a8-128">派生的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="250a8-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="250a8-129">如果`certificateValidationMode`属性为"自定义"，此类型的实例用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="250a8-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="250a8-130">子元素</span><span class="sxs-lookup"><span data-stu-id="250a8-130">Child Elements</span></span>  
 <span data-ttu-id="250a8-131">无</span><span class="sxs-lookup"><span data-stu-id="250a8-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="250a8-132">父元素</span><span class="sxs-lookup"><span data-stu-id="250a8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="250a8-133">元素</span><span class="sxs-lookup"><span data-stu-id="250a8-133">Element</span></span>|<span data-ttu-id="250a8-134">描述</span><span class="sxs-lookup"><span data-stu-id="250a8-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="250a8-135">\<add></span><span class="sxs-lookup"><span data-stu-id="250a8-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="250a8-136">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="250a8-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="250a8-137">示例</span><span class="sxs-lookup"><span data-stu-id="250a8-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
