---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 08082d2e6647f07f33df72ab79dac00c15a1cd1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200813"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="d4a46-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d4a46-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="d4a46-102">注册令牌处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="d4a46-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d4a46-103">颁发者令牌解析程序用于解决签名令牌对传入令牌和消息。</span><span class="sxs-lookup"><span data-stu-id="d4a46-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="d4a46-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d4a46-104">\<system.identityModel></span></span>  
<span data-ttu-id="d4a46-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d4a46-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d4a46-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d4a46-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d4a46-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d4a46-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d4a46-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d4a46-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a46-109">语法</span><span class="sxs-lookup"><span data-stu-id="d4a46-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4a46-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4a46-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d4a46-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d4a46-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4a46-112">特性</span><span class="sxs-lookup"><span data-stu-id="d4a46-112">Attributes</span></span>  
  
|<span data-ttu-id="d4a46-113">特性</span><span class="sxs-lookup"><span data-stu-id="d4a46-113">Attribute</span></span>|<span data-ttu-id="d4a46-114">描述</span><span class="sxs-lookup"><span data-stu-id="d4a46-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4a46-115">类型</span><span class="sxs-lookup"><span data-stu-id="d4a46-115">type</span></span>|<span data-ttu-id="d4a46-116">指定颁发者令牌解析器的类型。</span><span class="sxs-lookup"><span data-stu-id="d4a46-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="d4a46-117">必须是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类或派生类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="d4a46-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="d4a46-118">必需。</span><span class="sxs-lookup"><span data-stu-id="d4a46-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4a46-119">子元素</span><span class="sxs-lookup"><span data-stu-id="d4a46-119">Child Elements</span></span>  
 <span data-ttu-id="d4a46-120">None</span><span class="sxs-lookup"><span data-stu-id="d4a46-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4a46-121">父元素</span><span class="sxs-lookup"><span data-stu-id="d4a46-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d4a46-122">元素</span><span class="sxs-lookup"><span data-stu-id="d4a46-122">Element</span></span>|<span data-ttu-id="d4a46-123">描述</span><span class="sxs-lookup"><span data-stu-id="d4a46-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4a46-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d4a46-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d4a46-125">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="d4a46-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4a46-126">备注</span><span class="sxs-lookup"><span data-stu-id="d4a46-126">Remarks</span></span>  
 <span data-ttu-id="d4a46-127">颁发者令牌解析程序用于解决签名令牌对传入令牌和消息。</span><span class="sxs-lookup"><span data-stu-id="d4a46-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="d4a46-128">它用于检索用来检查签名的加密材料。</span><span class="sxs-lookup"><span data-stu-id="d4a46-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="d4a46-129">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="d4a46-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="d4a46-130">指定的类型可以是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生的自定义类型或<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="d4a46-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="d4a46-131">一些令牌处理程序，可在配置中指定颁发者令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="d4a46-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="d4a46-132">单个标记处理程序上的设置将覆盖指定安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="d4a46-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4a46-133">指定`<issuerTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="d4a46-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d4a46-134">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="d4a46-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4a46-135">示例</span><span class="sxs-lookup"><span data-stu-id="d4a46-135">Example</span></span>  
 <span data-ttu-id="d4a46-136">以下 XML 显示了配置为颁发者令牌解析程序基于派生的自定义类<xref:System.IdentityModel.Tokens.IssuerTokenResolver>。</span><span class="sxs-lookup"><span data-stu-id="d4a46-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="d4a46-137">令牌解析器维护自定义配置元素中初始化受众密钥对的字典 (`<AddAudienceKeyPair>`) 为类定义。</span><span class="sxs-lookup"><span data-stu-id="d4a46-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="d4a46-138">此类替代<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>方法来处理此元素。</span><span class="sxs-lookup"><span data-stu-id="d4a46-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="d4a46-139">在下面的示例; 显示重写但是，它将调用的方法不会显示为简洁起见。</span><span class="sxs-lookup"><span data-stu-id="d4a46-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="d4a46-140">有关完整示例，请参阅`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="d4a46-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="d4a46-141">示例</span><span class="sxs-lookup"><span data-stu-id="d4a46-141">Example</span></span>  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4a46-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4a46-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
