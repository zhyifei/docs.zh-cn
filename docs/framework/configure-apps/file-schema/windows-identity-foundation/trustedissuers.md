---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 32aad3529ded6d0234b1bcb388ecbbc3b0a11c87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944270"
---
# <a name="trustedissuers"></a><span data-ttu-id="e0389-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="e0389-101">\<trustedIssuers></span></span>
<span data-ttu-id="e0389-102">配置基于配置的颁发者名称注册表 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>) 使用的受信任颁发者证书的列表。</span><span class="sxs-lookup"><span data-stu-id="e0389-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="e0389-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e0389-103">\<system.identityModel></span></span>  
<span data-ttu-id="e0389-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e0389-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e0389-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e0389-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e0389-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="e0389-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="e0389-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="e0389-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="e0389-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="e0389-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0389-109">语法</span><span class="sxs-lookup"><span data-stu-id="e0389-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0389-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e0389-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e0389-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e0389-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0389-112">特性</span><span class="sxs-lookup"><span data-stu-id="e0389-112">Attributes</span></span>  
 <span data-ttu-id="e0389-113">无</span><span class="sxs-lookup"><span data-stu-id="e0389-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e0389-114">子元素</span><span class="sxs-lookup"><span data-stu-id="e0389-114">Child Elements</span></span>  
  
|<span data-ttu-id="e0389-115">元素</span><span class="sxs-lookup"><span data-stu-id="e0389-115">Element</span></span>|<span data-ttu-id="e0389-116">描述</span><span class="sxs-lookup"><span data-stu-id="e0389-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="e0389-117">将证书添加到受信任的颁发者的集合中。</span><span class="sxs-lookup"><span data-stu-id="e0389-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="e0389-118">证书是用`thumbprint`属性指定的。</span><span class="sxs-lookup"><span data-stu-id="e0389-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="e0389-119">此属性是必需的, 并且应该包含证书指纹的 ASN. 1 编码形式。</span><span class="sxs-lookup"><span data-stu-id="e0389-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="e0389-120">属性`name`是可选的, 可用于指定证书的友好名称。</span><span class="sxs-lookup"><span data-stu-id="e0389-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="e0389-121">从受信任的颁发者集合中清除所有证书。</span><span class="sxs-lookup"><span data-stu-id="e0389-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="e0389-122">从受信任的颁发者集合中删除证书。</span><span class="sxs-lookup"><span data-stu-id="e0389-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="e0389-123">证书是用`thumbprint`属性指定的。</span><span class="sxs-lookup"><span data-stu-id="e0389-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="e0389-124">该属性是必选项。</span><span class="sxs-lookup"><span data-stu-id="e0389-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0389-125">父元素</span><span class="sxs-lookup"><span data-stu-id="e0389-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e0389-126">元素</span><span class="sxs-lookup"><span data-stu-id="e0389-126">Element</span></span>|<span data-ttu-id="e0389-127">描述</span><span class="sxs-lookup"><span data-stu-id="e0389-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0389-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="e0389-128">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="e0389-129">配置颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="e0389-129">Configures the issuer name registry.</span></span> <span data-ttu-id="e0389-130">**重要提示：** 元素的<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>属性必须引用类, 才能使元素有效。`<trustedIssuers>` `type` `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="e0389-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0389-131">备注</span><span class="sxs-lookup"><span data-stu-id="e0389-131">Remarks</span></span>  
 <span data-ttu-id="e0389-132">Windows Identity Foundation (WIF) 提供<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类的单一实现类<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> , 该类是类的一种实现。</span><span class="sxs-lookup"><span data-stu-id="e0389-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="e0389-133">配置颁发者名称注册表将维护从配置加载的受信任颁发者的列表。</span><span class="sxs-lookup"><span data-stu-id="e0389-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="e0389-134">此列表将每个颁发者名称与 x.509 证书关联, 该证书是验证颁发者生成的令牌签名所需的证书。</span><span class="sxs-lookup"><span data-stu-id="e0389-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="e0389-135">受信任颁发者证书的列表是在`<trustedIssuers>`元素下指定的。</span><span class="sxs-lookup"><span data-stu-id="e0389-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="e0389-136">列表中的每个元素都将助记键颁发者名称与 x.509 证书关联, 该证书是验证该颁发者生成的令牌签名所需的。</span><span class="sxs-lookup"><span data-stu-id="e0389-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="e0389-137">受信任的证书是使用 "证书指纹" 的 "ASN. 1" 编码形式指定的, 并`<add>`使用元素添加集合。</span><span class="sxs-lookup"><span data-stu-id="e0389-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="e0389-138">您可以使用`<clear>`和`<remove>`元素从列表中清除或删除颁发者 (证书)。</span><span class="sxs-lookup"><span data-stu-id="e0389-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="e0389-139">元素的<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>属性必须引用类, 才能使元素有效。`<trustedIssuers>` `type` `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="e0389-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0389-140">示例</span><span class="sxs-lookup"><span data-stu-id="e0389-140">Example</span></span>  
 <span data-ttu-id="e0389-141">下面的 XML 演示如何指定基于配置的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="e0389-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0389-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0389-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
