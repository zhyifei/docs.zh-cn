---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790437"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="56833-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="56833-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="56833-102">提供的可选配置<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="56833-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="56833-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="56833-103">\<system.identityModel></span></span>  
<span data-ttu-id="56833-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="56833-104">\<identityConfiguration></span></span>  
<span data-ttu-id="56833-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="56833-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="56833-106">\<add></span><span class="sxs-lookup"><span data-stu-id="56833-106">\<add></span></span>  
<span data-ttu-id="56833-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="56833-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56833-108">语法</span><span class="sxs-lookup"><span data-stu-id="56833-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56833-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="56833-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56833-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="56833-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56833-111">特性</span><span class="sxs-lookup"><span data-stu-id="56833-111">Attributes</span></span>  
  
|<span data-ttu-id="56833-112">特性</span><span class="sxs-lookup"><span data-stu-id="56833-112">Attribute</span></span>|<span data-ttu-id="56833-113">描述</span><span class="sxs-lookup"><span data-stu-id="56833-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56833-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="56833-114">certificateValidationMode</span></span>|<span data-ttu-id="56833-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。</span><span class="sxs-lookup"><span data-stu-id="56833-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="56833-116">默认值为"PeerOrChainTrust"。</span><span class="sxs-lookup"><span data-stu-id="56833-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="56833-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="56833-117">mapToWindows</span></span>|<span data-ttu-id="56833-118">指定的标记处理程序是否应使用传入 UPN 声明到 Windows 帐户映射验证令牌。</span><span class="sxs-lookup"><span data-stu-id="56833-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="56833-119">默认值为"false"。</span><span class="sxs-lookup"><span data-stu-id="56833-119">The default is "false".</span></span>|  
|<span data-ttu-id="56833-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="56833-120">revocationMode</span></span>|<span data-ttu-id="56833-121"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。</span><span class="sxs-lookup"><span data-stu-id="56833-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="56833-122">默认值为"联机"。</span><span class="sxs-lookup"><span data-stu-id="56833-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="56833-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="56833-123">trustedStoreLocation</span></span>|<span data-ttu-id="56833-124">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="56833-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="56833-125">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="56833-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="56833-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="56833-126">certificateValidator</span></span>|<span data-ttu-id="56833-127">派生的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="56833-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="56833-128">如果`certificateValidationMode`属性为"自定义"，此类型的实例用于颁发者证书验证。</span><span class="sxs-lookup"><span data-stu-id="56833-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56833-129">子元素</span><span class="sxs-lookup"><span data-stu-id="56833-129">Child Elements</span></span>  
 <span data-ttu-id="56833-130">None</span><span class="sxs-lookup"><span data-stu-id="56833-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56833-131">父元素</span><span class="sxs-lookup"><span data-stu-id="56833-131">Parent Elements</span></span>  
  
|<span data-ttu-id="56833-132">元素</span><span class="sxs-lookup"><span data-stu-id="56833-132">Element</span></span>|<span data-ttu-id="56833-133">描述</span><span class="sxs-lookup"><span data-stu-id="56833-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56833-134">\<add></span><span class="sxs-lookup"><span data-stu-id="56833-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="56833-135">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="56833-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="56833-136">示例</span><span class="sxs-lookup"><span data-stu-id="56833-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
