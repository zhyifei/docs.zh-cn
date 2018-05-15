---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 646833f277c3ef4675a835ca0af3daf647e01224
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="f5bb1-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="f5bb1-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="f5bb1-103">注册的颁发者令牌解析程序由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f5bb1-104">颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="f5bb1-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f5bb1-105">\<system.identityModel></span></span>  
<span data-ttu-id="f5bb1-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f5bb1-106">\<identityConfiguration></span></span>  
<span data-ttu-id="f5bb1-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f5bb1-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f5bb1-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f5bb1-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f5bb1-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="f5bb1-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5bb1-110">语法</span><span class="sxs-lookup"><span data-stu-id="f5bb1-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5bb1-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f5bb1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5bb1-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5bb1-113">特性</span><span class="sxs-lookup"><span data-stu-id="f5bb1-113">Attributes</span></span>  
  
|<span data-ttu-id="f5bb1-114">特性</span><span class="sxs-lookup"><span data-stu-id="f5bb1-114">Attribute</span></span>|<span data-ttu-id="f5bb1-115">描述</span><span class="sxs-lookup"><span data-stu-id="f5bb1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5bb1-116">类型</span><span class="sxs-lookup"><span data-stu-id="f5bb1-116">type</span></span>|<span data-ttu-id="f5bb1-117">指定颁发者令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="f5bb1-118">必须为<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类或派生自类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="f5bb1-119">必须的。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5bb1-120">子元素</span><span class="sxs-lookup"><span data-stu-id="f5bb1-120">Child Elements</span></span>  
 <span data-ttu-id="f5bb1-121">无</span><span class="sxs-lookup"><span data-stu-id="f5bb1-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5bb1-122">父元素</span><span class="sxs-lookup"><span data-stu-id="f5bb1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f5bb1-123">元素</span><span class="sxs-lookup"><span data-stu-id="f5bb1-123">Element</span></span>|<span data-ttu-id="f5bb1-124">描述</span><span class="sxs-lookup"><span data-stu-id="f5bb1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5bb1-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f5bb1-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="f5bb1-126">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5bb1-127">备注</span><span class="sxs-lookup"><span data-stu-id="f5bb1-127">Remarks</span></span>  
 <span data-ttu-id="f5bb1-128">颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="f5bb1-129">它用于检索用于检查签名的加密材料。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="f5bb1-130">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="f5bb1-131">指定的类型可以是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>或派生自的自定义类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="f5bb1-132">某些令牌处理程序，可以在配置中指定颁发者的标记解析程序设置。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="f5bb1-133">对于单个令牌处理程序的设置会覆盖上的安全令牌的处理程序集合的指定。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5bb1-134">指定`<issuerTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f5bb1-135">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5bb1-136">示例</span><span class="sxs-lookup"><span data-stu-id="f5bb1-136">Example</span></span>  
 <span data-ttu-id="f5bb1-137">下面的 XML 演示基于自定义类派生自颁发者令牌解析程序的配置<xref:System.IdentityModel.Tokens.IssuerTokenResolver>。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="f5bb1-138">令牌解析程序维护的受众密钥对的自定义配置元素中初始化字典 (`<AddAudienceKeyPair>`) 为类定义。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="f5bb1-139">类将重写<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>方法来处理此元素。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="f5bb1-140">重写显示在下面的示例;但是，它调用的方法不会显示为简洁起见中。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="f5bb1-141">有关完整示例，请参阅`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="f5bb1-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="f5bb1-142">示例</span><span class="sxs-lookup"><span data-stu-id="f5bb1-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5bb1-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5bb1-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
