---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: eefd18c206b7f013c3a423df424c795583c0dde8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216326"
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="07cf6-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="07cf6-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="07cf6-103">注册令牌处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="07cf6-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="07cf6-104">颁发者令牌解析程序用于解决签名令牌对传入令牌和消息。</span><span class="sxs-lookup"><span data-stu-id="07cf6-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="07cf6-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="07cf6-105">\<system.identityModel></span></span>  
<span data-ttu-id="07cf6-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="07cf6-106">\<identityConfiguration></span></span>  
<span data-ttu-id="07cf6-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="07cf6-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="07cf6-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="07cf6-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="07cf6-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="07cf6-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07cf6-110">语法</span><span class="sxs-lookup"><span data-stu-id="07cf6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07cf6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="07cf6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="07cf6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="07cf6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07cf6-113">特性</span><span class="sxs-lookup"><span data-stu-id="07cf6-113">Attributes</span></span>  
  
|<span data-ttu-id="07cf6-114">特性</span><span class="sxs-lookup"><span data-stu-id="07cf6-114">Attribute</span></span>|<span data-ttu-id="07cf6-115">描述</span><span class="sxs-lookup"><span data-stu-id="07cf6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07cf6-116">类型</span><span class="sxs-lookup"><span data-stu-id="07cf6-116">type</span></span>|<span data-ttu-id="07cf6-117">指定颁发者令牌解析器的类型。</span><span class="sxs-lookup"><span data-stu-id="07cf6-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="07cf6-118">必须是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类或派生类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="07cf6-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="07cf6-119">必须的。</span><span class="sxs-lookup"><span data-stu-id="07cf6-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07cf6-120">子元素</span><span class="sxs-lookup"><span data-stu-id="07cf6-120">Child Elements</span></span>  
 <span data-ttu-id="07cf6-121">无</span><span class="sxs-lookup"><span data-stu-id="07cf6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07cf6-122">父元素</span><span class="sxs-lookup"><span data-stu-id="07cf6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="07cf6-123">元素</span><span class="sxs-lookup"><span data-stu-id="07cf6-123">Element</span></span>|<span data-ttu-id="07cf6-124">描述</span><span class="sxs-lookup"><span data-stu-id="07cf6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07cf6-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="07cf6-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="07cf6-126">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="07cf6-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07cf6-127">备注</span><span class="sxs-lookup"><span data-stu-id="07cf6-127">Remarks</span></span>  
 <span data-ttu-id="07cf6-128">颁发者令牌解析程序用于解决签名令牌对传入令牌和消息。</span><span class="sxs-lookup"><span data-stu-id="07cf6-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="07cf6-129">它用于检索用来检查签名的加密材料。</span><span class="sxs-lookup"><span data-stu-id="07cf6-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="07cf6-130">必须指定`type`属性。</span><span class="sxs-lookup"><span data-stu-id="07cf6-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="07cf6-131">指定的类型可以是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生的自定义类型或<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。</span><span class="sxs-lookup"><span data-stu-id="07cf6-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="07cf6-132">一些令牌处理程序，可在配置中指定颁发者令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="07cf6-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="07cf6-133">单个标记处理程序上的设置将覆盖指定安全标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="07cf6-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07cf6-134">指定`<issuerTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="07cf6-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="07cf6-135">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="07cf6-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07cf6-136">示例</span><span class="sxs-lookup"><span data-stu-id="07cf6-136">Example</span></span>  
 <span data-ttu-id="07cf6-137">以下 XML 显示了配置为颁发者令牌解析程序基于派生的自定义类<xref:System.IdentityModel.Tokens.IssuerTokenResolver>。</span><span class="sxs-lookup"><span data-stu-id="07cf6-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="07cf6-138">令牌解析器维护自定义配置元素中初始化受众密钥对的字典 (`<AddAudienceKeyPair>`) 为类定义。</span><span class="sxs-lookup"><span data-stu-id="07cf6-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="07cf6-139">此类替代<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>方法来处理此元素。</span><span class="sxs-lookup"><span data-stu-id="07cf6-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="07cf6-140">在下面的示例; 显示重写但是，它将调用的方法不会显示为简洁起见。</span><span class="sxs-lookup"><span data-stu-id="07cf6-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="07cf6-141">有关完整示例，请参阅`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="07cf6-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="07cf6-142">示例</span><span class="sxs-lookup"><span data-stu-id="07cf6-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07cf6-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="07cf6-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
