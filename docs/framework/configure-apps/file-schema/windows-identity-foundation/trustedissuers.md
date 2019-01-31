---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: bb4cb5178885b90ef25ee827c2f11593ead6e73d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276674"
---
# <a name="trustedissuers"></a><span data-ttu-id="d3236-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="d3236-101">\<trustedIssuers></span></span>
<span data-ttu-id="d3236-102">配置使用的基于配置的颁布者名称注册表的受信任的颁发者证书的列表 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>)。</span><span class="sxs-lookup"><span data-stu-id="d3236-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="d3236-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d3236-103">\<system.identityModel></span></span>  
<span data-ttu-id="d3236-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d3236-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d3236-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d3236-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d3236-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d3236-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d3236-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d3236-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="d3236-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="d3236-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3236-109">语法</span><span class="sxs-lookup"><span data-stu-id="d3236-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3236-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d3236-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d3236-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d3236-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3236-112">特性</span><span class="sxs-lookup"><span data-stu-id="d3236-112">Attributes</span></span>  
 <span data-ttu-id="d3236-113">无</span><span class="sxs-lookup"><span data-stu-id="d3236-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d3236-114">子元素</span><span class="sxs-lookup"><span data-stu-id="d3236-114">Child Elements</span></span>  
  
|<span data-ttu-id="d3236-115">元素</span><span class="sxs-lookup"><span data-stu-id="d3236-115">Element</span></span>|<span data-ttu-id="d3236-116">描述</span><span class="sxs-lookup"><span data-stu-id="d3236-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="d3236-117">将证书添加到受信任颁发者的集合。</span><span class="sxs-lookup"><span data-stu-id="d3236-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="d3236-118">使用指定的证书`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="d3236-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="d3236-119">此属性是必需的并且应包含证书指纹的 ASN.1 编码形式。</span><span class="sxs-lookup"><span data-stu-id="d3236-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="d3236-120">`name`属性是可选的可用于指定证书的友好名称。</span><span class="sxs-lookup"><span data-stu-id="d3236-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="d3236-121">清除所有证书从受信任颁发者的集合。</span><span class="sxs-lookup"><span data-stu-id="d3236-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="d3236-122">从受信任颁发者集合中删除证书。</span><span class="sxs-lookup"><span data-stu-id="d3236-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="d3236-123">使用指定的证书`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="d3236-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="d3236-124">该属性是必选项。</span><span class="sxs-lookup"><span data-stu-id="d3236-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3236-125">父元素</span><span class="sxs-lookup"><span data-stu-id="d3236-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d3236-126">元素</span><span class="sxs-lookup"><span data-stu-id="d3236-126">Element</span></span>|<span data-ttu-id="d3236-127">描述</span><span class="sxs-lookup"><span data-stu-id="d3236-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3236-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d3236-128">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="d3236-129">配置颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="d3236-129">Configures the issuer name registry.</span></span> <span data-ttu-id="d3236-130">**重要提示：**`type`的属性`<issuerNameRegistry>`元素必须引用<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类`<trustedIssuers>`元素有效。</span><span class="sxs-lookup"><span data-stu-id="d3236-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3236-131">备注</span><span class="sxs-lookup"><span data-stu-id="d3236-131">Remarks</span></span>  
 <span data-ttu-id="d3236-132">Windows Identity Foundation (WIF) 提供的单一实现<xref:System.IdentityModel.Tokens.IssuerNameRegistry>默认情况下，类<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="d3236-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d3236-133">配置颁发者名称注册表维护从配置中加载的受信任颁发者列表。</span><span class="sxs-lookup"><span data-stu-id="d3236-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="d3236-134">列表将与所需验证颁发者生成的令牌签名的 X.509 证书关联的每个颁发者名称。</span><span class="sxs-lookup"><span data-stu-id="d3236-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="d3236-135">在指定的受信任的颁发者证书的列表`<trustedIssuers>`元素。</span><span class="sxs-lookup"><span data-stu-id="d3236-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="d3236-136">在列表中的每个元素将与验证生成的该颁发者的令牌签名所需的 X.509 证书关联的助记键的颁发者名称。</span><span class="sxs-lookup"><span data-stu-id="d3236-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="d3236-137">受信任的证书使用 ASN.1 编码的证书指纹的形式指定，并且通过使用添加集合`<add>`元素。</span><span class="sxs-lookup"><span data-stu-id="d3236-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="d3236-138">您可以清除或通过从列表中删除 （证书） 的颁发者`<clear>`和`<remove>`元素。</span><span class="sxs-lookup"><span data-stu-id="d3236-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d3236-139">`type`的属性`<issuerNameRegistry>`元素必须引用<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类`<trustedIssuers>`元素有效。</span><span class="sxs-lookup"><span data-stu-id="d3236-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3236-140">示例</span><span class="sxs-lookup"><span data-stu-id="d3236-140">Example</span></span>  
 <span data-ttu-id="d3236-141">下面的 XML 演示如何指定配置基于颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="d3236-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3236-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3236-142">See also</span></span>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
