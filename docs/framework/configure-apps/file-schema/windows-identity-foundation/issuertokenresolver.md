---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: da591940910b16d42ef8ab1a05c4b244dbe543f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942631"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="1512d-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1512d-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="1512d-102">注册由标记处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="1512d-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="1512d-103">颁发者令牌解析器用于解析传入令牌和消息的签名令牌。</span><span class="sxs-lookup"><span data-stu-id="1512d-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="1512d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1512d-104">\<system.identityModel></span></span>  
<span data-ttu-id="1512d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1512d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1512d-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="1512d-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1512d-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1512d-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="1512d-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1512d-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1512d-109">语法</span><span class="sxs-lookup"><span data-stu-id="1512d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1512d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1512d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1512d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1512d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1512d-112">特性</span><span class="sxs-lookup"><span data-stu-id="1512d-112">Attributes</span></span>  
  
|<span data-ttu-id="1512d-113">特性</span><span class="sxs-lookup"><span data-stu-id="1512d-113">Attribute</span></span>|<span data-ttu-id="1512d-114">描述</span><span class="sxs-lookup"><span data-stu-id="1512d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1512d-115">type</span><span class="sxs-lookup"><span data-stu-id="1512d-115">type</span></span>|<span data-ttu-id="1512d-116">指定颁发者令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="1512d-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="1512d-117">必须是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类或派生<xref:System.IdentityModel.Tokens.IssuerTokenResolver>自类的类型。</span><span class="sxs-lookup"><span data-stu-id="1512d-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="1512d-118">必需。</span><span class="sxs-lookup"><span data-stu-id="1512d-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1512d-119">子元素</span><span class="sxs-lookup"><span data-stu-id="1512d-119">Child Elements</span></span>  
 <span data-ttu-id="1512d-120">无</span><span class="sxs-lookup"><span data-stu-id="1512d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1512d-121">父元素</span><span class="sxs-lookup"><span data-stu-id="1512d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1512d-122">元素</span><span class="sxs-lookup"><span data-stu-id="1512d-122">Element</span></span>|<span data-ttu-id="1512d-123">描述</span><span class="sxs-lookup"><span data-stu-id="1512d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1512d-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1512d-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="1512d-125">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="1512d-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1512d-126">备注</span><span class="sxs-lookup"><span data-stu-id="1512d-126">Remarks</span></span>  
 <span data-ttu-id="1512d-127">颁发者令牌解析器用于解析传入令牌和消息的签名令牌。</span><span class="sxs-lookup"><span data-stu-id="1512d-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="1512d-128">它用于检索用于检查签名的加密材料。</span><span class="sxs-lookup"><span data-stu-id="1512d-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="1512d-129">您必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="1512d-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="1512d-130">指定的类型可以是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>或<xref:System.IdentityModel.Tokens.IssuerTokenResolver>从类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="1512d-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="1512d-131">某些标记处理程序允许您在配置中指定颁发者令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="1512d-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="1512d-132">各个标记处理程序上的设置将替代在安全令牌处理程序集合中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="1512d-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1512d-133">将元素指定为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用, 但仍支持向后兼容。 `<issuerTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="1512d-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="1512d-134">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="1512d-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1512d-135">示例</span><span class="sxs-lookup"><span data-stu-id="1512d-135">Example</span></span>  
 <span data-ttu-id="1512d-136">下面的 XML 显示基于从<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生的自定义类的颁发者令牌解析程序的配置。</span><span class="sxs-lookup"><span data-stu-id="1512d-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="1512d-137">令牌解析程序维护从为类定义的自定义配置元素 (`<AddAudienceKeyPair>`) 初始化的访问群体-密钥对的字典。</span><span class="sxs-lookup"><span data-stu-id="1512d-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="1512d-138">类将重写<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>方法来处理此元素。</span><span class="sxs-lookup"><span data-stu-id="1512d-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="1512d-139">下面的示例显示了替代:但对于简洁起见, 它调用的方法不会显示。</span><span class="sxs-lookup"><span data-stu-id="1512d-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="1512d-140">有关完整的示例, 请参阅`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="1512d-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="1512d-141">示例</span><span class="sxs-lookup"><span data-stu-id="1512d-141">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1512d-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1512d-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
