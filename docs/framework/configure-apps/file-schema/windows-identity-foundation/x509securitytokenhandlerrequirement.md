---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 66d4e0d6a121f807f5f372b3f39577b0bb3c4ca6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="23cdd-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="23cdd-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="23cdd-103">提供的可选配置<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="23cdd-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="23cdd-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="23cdd-104">\<system.identityModel></span></span>  
<span data-ttu-id="23cdd-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="23cdd-105">\<identityConfiguration></span></span>  
<span data-ttu-id="23cdd-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="23cdd-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="23cdd-107">\<add></span><span class="sxs-lookup"><span data-stu-id="23cdd-107">\<add></span></span>  
<span data-ttu-id="23cdd-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="23cdd-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23cdd-109">语法</span><span class="sxs-lookup"><span data-stu-id="23cdd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23cdd-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23cdd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="23cdd-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="23cdd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23cdd-112">特性</span><span class="sxs-lookup"><span data-stu-id="23cdd-112">Attributes</span></span>  
  
|<span data-ttu-id="23cdd-113">特性</span><span class="sxs-lookup"><span data-stu-id="23cdd-113">Attribute</span></span>|<span data-ttu-id="23cdd-114">描述</span><span class="sxs-lookup"><span data-stu-id="23cdd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23cdd-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="23cdd-115">certificateValidationMode</span></span>|<span data-ttu-id="23cdd-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="23cdd-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="23cdd-117">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="23cdd-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="23cdd-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="23cdd-118">mapToWindows</span></span>|<span data-ttu-id="23cdd-119">指定令牌处理程序是否应通过使用传入的 UPN 声明到 Windows 帐户映射验证令牌。</span><span class="sxs-lookup"><span data-stu-id="23cdd-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="23cdd-120">默认值为"false"。</span><span class="sxs-lookup"><span data-stu-id="23cdd-120">The default is "false".</span></span>|  
|<span data-ttu-id="23cdd-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="23cdd-121">revocationMode</span></span>|<span data-ttu-id="23cdd-122"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="23cdd-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="23cdd-123">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="23cdd-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="23cdd-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="23cdd-124">trustedStoreLocation</span></span>|<span data-ttu-id="23cdd-125">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="23cdd-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="23cdd-126">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="23cdd-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="23cdd-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="23cdd-127">certificateValidator</span></span>|<span data-ttu-id="23cdd-128">派生自的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="23cdd-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="23cdd-129">如果`certificateValidationMode`属性为"Custom"，此类型的实例将使用颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="23cdd-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23cdd-130">子元素</span><span class="sxs-lookup"><span data-stu-id="23cdd-130">Child Elements</span></span>  
 <span data-ttu-id="23cdd-131">无</span><span class="sxs-lookup"><span data-stu-id="23cdd-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23cdd-132">父元素</span><span class="sxs-lookup"><span data-stu-id="23cdd-132">Parent Elements</span></span>  
  
|<span data-ttu-id="23cdd-133">元素</span><span class="sxs-lookup"><span data-stu-id="23cdd-133">Element</span></span>|<span data-ttu-id="23cdd-134">说明</span><span class="sxs-lookup"><span data-stu-id="23cdd-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23cdd-135">\<add></span><span class="sxs-lookup"><span data-stu-id="23cdd-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="23cdd-136">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="23cdd-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23cdd-137">示例</span><span class="sxs-lookup"><span data-stu-id="23cdd-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
