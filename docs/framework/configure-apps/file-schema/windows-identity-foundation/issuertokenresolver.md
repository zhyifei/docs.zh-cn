---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968511"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="2f990-101">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="2f990-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="2f990-102">注册由标记处理程序集合中的处理程序使用的颁发者令牌解析程序。</span><span class="sxs-lookup"><span data-stu-id="2f990-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="2f990-103">颁发者令牌解析器用于解析传入令牌和消息的签名令牌。</span><span class="sxs-lookup"><span data-stu-id="2f990-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="2f990-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f990-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f990-105">&nbsp;&nbsp;[ **\<system.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f990-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="2f990-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2f990-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="2f990-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="2f990-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="2f990-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="2f990-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="2f990-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="2f990-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f990-110">语法</span><span class="sxs-lookup"><span data-stu-id="2f990-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f990-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2f990-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2f990-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2f990-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f990-113">特性</span><span class="sxs-lookup"><span data-stu-id="2f990-113">Attributes</span></span>  
  
|<span data-ttu-id="2f990-114">特性</span><span class="sxs-lookup"><span data-stu-id="2f990-114">Attribute</span></span>|<span data-ttu-id="2f990-115">描述</span><span class="sxs-lookup"><span data-stu-id="2f990-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f990-116">类型</span><span class="sxs-lookup"><span data-stu-id="2f990-116">type</span></span>|<span data-ttu-id="2f990-117">指定颁发者令牌解析程序的类型。</span><span class="sxs-lookup"><span data-stu-id="2f990-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="2f990-118">必须是 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 类或派生自 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 类的类型。</span><span class="sxs-lookup"><span data-stu-id="2f990-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="2f990-119">必须的。</span><span class="sxs-lookup"><span data-stu-id="2f990-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f990-120">子元素</span><span class="sxs-lookup"><span data-stu-id="2f990-120">Child Elements</span></span>  
 <span data-ttu-id="2f990-121">None</span><span class="sxs-lookup"><span data-stu-id="2f990-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f990-122">父元素</span><span class="sxs-lookup"><span data-stu-id="2f990-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2f990-123">元素</span><span class="sxs-lookup"><span data-stu-id="2f990-123">Element</span></span>|<span data-ttu-id="2f990-124">描述</span><span class="sxs-lookup"><span data-stu-id="2f990-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f990-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2f990-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="2f990-126">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="2f990-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f990-127">备注</span><span class="sxs-lookup"><span data-stu-id="2f990-127">Remarks</span></span>  
 <span data-ttu-id="2f990-128">颁发者令牌解析器用于解析传入令牌和消息的签名令牌。</span><span class="sxs-lookup"><span data-stu-id="2f990-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="2f990-129">它用于检索用于检查签名的加密材料。</span><span class="sxs-lookup"><span data-stu-id="2f990-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="2f990-130">您必须指定 `type` 特性。</span><span class="sxs-lookup"><span data-stu-id="2f990-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="2f990-131">指定的类型可以是 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 或从 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="2f990-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="2f990-132">某些标记处理程序允许您在配置中指定颁发者令牌解析器设置。</span><span class="sxs-lookup"><span data-stu-id="2f990-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="2f990-133">各个标记处理程序上的设置将替代在安全令牌处理程序集合中指定的设置。</span><span class="sxs-lookup"><span data-stu-id="2f990-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f990-134">将 `<issuerTokenResolver>` 元素指定为[\<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="2f990-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="2f990-135">`<securityTokenHandlerConfiguration>` 元素上的设置将覆盖 `<identityConfiguration>` 元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="2f990-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f990-136">示例</span><span class="sxs-lookup"><span data-stu-id="2f990-136">Example</span></span>  
 <span data-ttu-id="2f990-137">下面的 XML 演示颁发者令牌解析程序的配置，该解析程序基于从 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生的自定义类。</span><span class="sxs-lookup"><span data-stu-id="2f990-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="2f990-138">令牌解析程序维护从为类定义的自定义配置元素（`<AddAudienceKeyPair>`）初始化的受众密钥对字典。</span><span class="sxs-lookup"><span data-stu-id="2f990-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="2f990-139">类将重写 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 方法来处理此元素。</span><span class="sxs-lookup"><span data-stu-id="2f990-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="2f990-140">下面的示例显示了替代：但对于简洁起见，它调用的方法不会显示。</span><span class="sxs-lookup"><span data-stu-id="2f990-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="2f990-141">有关完整示例，请参阅 `CustomToken` 示例。</span><span class="sxs-lookup"><span data-stu-id="2f990-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="2f990-142">示例</span><span class="sxs-lookup"><span data-stu-id="2f990-142">Example</span></span>
  
```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="2f990-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f990-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
