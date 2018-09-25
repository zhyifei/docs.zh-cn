---
title: '&lt;trustedIssuers&gt;'
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: c390cecc265b27dfa8d9d0a892f5930c982f7054
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075367"
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="63fe9-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="63fe9-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="63fe9-103">配置使用的基于配置的颁布者名称注册表的受信任的颁发者证书的列表 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>)。</span><span class="sxs-lookup"><span data-stu-id="63fe9-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="63fe9-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="63fe9-104">\<system.identityModel></span></span>  
<span data-ttu-id="63fe9-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="63fe9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="63fe9-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="63fe9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="63fe9-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="63fe9-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="63fe9-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="63fe9-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="63fe9-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="63fe9-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63fe9-110">语法</span><span class="sxs-lookup"><span data-stu-id="63fe9-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63fe9-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63fe9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="63fe9-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63fe9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63fe9-113">特性</span><span class="sxs-lookup"><span data-stu-id="63fe9-113">Attributes</span></span>  
 <span data-ttu-id="63fe9-114">无</span><span class="sxs-lookup"><span data-stu-id="63fe9-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="63fe9-115">子元素</span><span class="sxs-lookup"><span data-stu-id="63fe9-115">Child Elements</span></span>  
  
|<span data-ttu-id="63fe9-116">元素</span><span class="sxs-lookup"><span data-stu-id="63fe9-116">Element</span></span>|<span data-ttu-id="63fe9-117">描述</span><span class="sxs-lookup"><span data-stu-id="63fe9-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="63fe9-118">将证书添加到受信任颁发者的集合。</span><span class="sxs-lookup"><span data-stu-id="63fe9-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="63fe9-119">使用指定的证书`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="63fe9-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="63fe9-120">此属性是必需的并且应包含证书指纹的 ASN.1 编码形式。</span><span class="sxs-lookup"><span data-stu-id="63fe9-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="63fe9-121">`name`属性是可选的可用于指定证书的友好名称。</span><span class="sxs-lookup"><span data-stu-id="63fe9-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="63fe9-122">清除所有证书从受信任颁发者的集合。</span><span class="sxs-lookup"><span data-stu-id="63fe9-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="63fe9-123">从受信任颁发者集合中删除证书。</span><span class="sxs-lookup"><span data-stu-id="63fe9-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="63fe9-124">使用指定的证书`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="63fe9-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="63fe9-125">该属性是必选项。</span><span class="sxs-lookup"><span data-stu-id="63fe9-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63fe9-126">父元素</span><span class="sxs-lookup"><span data-stu-id="63fe9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="63fe9-127">元素</span><span class="sxs-lookup"><span data-stu-id="63fe9-127">Element</span></span>|<span data-ttu-id="63fe9-128">描述</span><span class="sxs-lookup"><span data-stu-id="63fe9-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63fe9-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="63fe9-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="63fe9-130">配置颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="63fe9-130">Configures the issuer name registry.</span></span> <span data-ttu-id="63fe9-131">**重要说明：** `type`的属性`<issuerNameRegistry>`元素必须引用<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类`<trustedIssuers>`元素有效。</span><span class="sxs-lookup"><span data-stu-id="63fe9-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63fe9-132">备注</span><span class="sxs-lookup"><span data-stu-id="63fe9-132">Remarks</span></span>  
 <span data-ttu-id="63fe9-133">Windows Identity Foundation (WIF) 提供的单一实现<xref:System.IdentityModel.Tokens.IssuerNameRegistry>默认情况下，类<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="63fe9-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="63fe9-134">配置颁发者名称注册表维护从配置中加载的受信任颁发者列表。</span><span class="sxs-lookup"><span data-stu-id="63fe9-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="63fe9-135">列表将与所需验证颁发者生成的令牌签名的 X.509 证书关联的每个颁发者名称。</span><span class="sxs-lookup"><span data-stu-id="63fe9-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="63fe9-136">在指定的受信任的颁发者证书的列表`<trustedIssuers>`元素。</span><span class="sxs-lookup"><span data-stu-id="63fe9-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="63fe9-137">在列表中的每个元素将与验证生成的该颁发者的令牌签名所需的 X.509 证书关联的助记键的颁发者名称。</span><span class="sxs-lookup"><span data-stu-id="63fe9-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="63fe9-138">受信任的证书使用 ASN.1 编码的证书指纹的形式指定，并且通过使用添加集合`<add>`元素。</span><span class="sxs-lookup"><span data-stu-id="63fe9-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="63fe9-139">您可以清除或通过从列表中删除 （证书） 的颁发者`<clear>`和`<remove>`元素。</span><span class="sxs-lookup"><span data-stu-id="63fe9-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="63fe9-140">`type`的属性`<issuerNameRegistry>`元素必须引用<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类`<trustedIssuers>`元素有效。</span><span class="sxs-lookup"><span data-stu-id="63fe9-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63fe9-141">示例</span><span class="sxs-lookup"><span data-stu-id="63fe9-141">Example</span></span>  
 <span data-ttu-id="63fe9-142">下面的 XML 演示如何指定配置基于颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="63fe9-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="63fe9-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="63fe9-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
