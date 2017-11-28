---
title: '&lt;issuerTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 02e2beb285cb0c4d88f98c3155ab5a3ff5e31e0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="14978-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="14978-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="14978-103">注册的颁发者令牌解析程序由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="14978-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="14978-104">颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="14978-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="14978-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="14978-105">\<system.identityModel></span></span>  
<span data-ttu-id="14978-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="14978-106">\<identityConfiguration></span></span>  
<span data-ttu-id="14978-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="14978-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="14978-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="14978-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="14978-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="14978-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14978-110">语法</span><span class="sxs-lookup"><span data-stu-id="14978-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14978-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="14978-111">Attributes and Elements</span></span>  
 <span data-ttu-id="14978-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="14978-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14978-113">特性</span><span class="sxs-lookup"><span data-stu-id="14978-113">Attributes</span></span>  
  
|<span data-ttu-id="14978-114">特性</span><span class="sxs-lookup"><span data-stu-id="14978-114">Attribute</span></span>|<span data-ttu-id="14978-115">描述</span><span class="sxs-lookup"><span data-stu-id="14978-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14978-116">类型</span><span class="sxs-lookup"><span data-stu-id="14978-116">type</span></span>|<span data-ttu-id="14978-117">指定颁发者令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="14978-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="14978-118">必须为<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类或派生自类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="14978-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="14978-119">必需。</span><span class="sxs-lookup"><span data-stu-id="14978-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14978-120">子元素</span><span class="sxs-lookup"><span data-stu-id="14978-120">Child Elements</span></span>  
 <span data-ttu-id="14978-121">无</span><span class="sxs-lookup"><span data-stu-id="14978-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14978-122">父元素</span><span class="sxs-lookup"><span data-stu-id="14978-122">Parent Elements</span></span>  
  
|<span data-ttu-id="14978-123">元素</span><span class="sxs-lookup"><span data-stu-id="14978-123">Element</span></span>|<span data-ttu-id="14978-124">描述</span><span class="sxs-lookup"><span data-stu-id="14978-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14978-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="14978-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="14978-126">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="14978-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14978-127">备注</span><span class="sxs-lookup"><span data-stu-id="14978-127">Remarks</span></span>  
 <span data-ttu-id="14978-128">颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。</span><span class="sxs-lookup"><span data-stu-id="14978-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="14978-129">它用于检索用于检查签名的加密材料。</span><span class="sxs-lookup"><span data-stu-id="14978-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="14978-130">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="14978-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="14978-131">指定的类型可以是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>或派生自的自定义类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="14978-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="14978-132">某些令牌处理程序，可以在配置中指定颁发者的标记解析程序设置。</span><span class="sxs-lookup"><span data-stu-id="14978-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="14978-133">对于单个令牌处理程序的设置会覆盖上的安全令牌的处理程序集合的指定。</span><span class="sxs-lookup"><span data-stu-id="14978-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14978-134">指定`<issuerTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="14978-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="14978-135">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="14978-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14978-136">示例</span><span class="sxs-lookup"><span data-stu-id="14978-136">Example</span></span>  
 <span data-ttu-id="14978-137">下面的 XML 演示基于自定义类派生自颁发者令牌解析程序的配置<xref:System.IdentityModel.Tokens.IssuerTokenResolver>。</span><span class="sxs-lookup"><span data-stu-id="14978-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="14978-138">令牌解析程序维护的受众密钥对的自定义配置元素中初始化字典 (`<AddAudienceKeyPair>`) 为类定义。</span><span class="sxs-lookup"><span data-stu-id="14978-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="14978-139">类将重写<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>方法来处理此元素。</span><span class="sxs-lookup"><span data-stu-id="14978-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="14978-140">重写显示在下面的示例;但是，它调用的方法不会显示为简洁起见中。</span><span class="sxs-lookup"><span data-stu-id="14978-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="14978-141">有关完整示例，请参阅`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="14978-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="14978-142">示例</span><span class="sxs-lookup"><span data-stu-id="14978-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14978-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14978-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
