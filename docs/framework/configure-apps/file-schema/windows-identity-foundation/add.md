---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973804"
---
# <a name="add"></a><span data-ttu-id="f3cd4-101">\<add></span><span class="sxs-lookup"><span data-stu-id="f3cd4-101">\<add></span></span>
<span data-ttu-id="f3cd4-102">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="f3cd4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f3cd4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f3cd4-104">&nbsp;&nbsp;[ **\<system.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f3cd4-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f3cd4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f3cd4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f3cd4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="f3cd4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="f3cd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="f3cd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3cd4-108">语法</span><span class="sxs-lookup"><span data-stu-id="f3cd4-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3cd4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f3cd4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f3cd4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3cd4-111">特性</span><span class="sxs-lookup"><span data-stu-id="f3cd4-111">Attributes</span></span>  
  
|<span data-ttu-id="f3cd4-112">特性</span><span class="sxs-lookup"><span data-stu-id="f3cd4-112">Attribute</span></span>|<span data-ttu-id="f3cd4-113">描述</span><span class="sxs-lookup"><span data-stu-id="f3cd4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3cd4-114">类型</span><span class="sxs-lookup"><span data-stu-id="f3cd4-114">type</span></span>|<span data-ttu-id="f3cd4-115">要添加的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="f3cd4-116">有关如何指定 `type` 属性的详细信息，请参阅[自定义类型引用](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3cd4-117">子元素</span><span class="sxs-lookup"><span data-stu-id="f3cd4-117">Child Elements</span></span>  
  
|<span data-ttu-id="f3cd4-118">元素</span><span class="sxs-lookup"><span data-stu-id="f3cd4-118">Element</span></span>|<span data-ttu-id="f3cd4-119">描述</span><span class="sxs-lookup"><span data-stu-id="f3cd4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3cd4-120">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="f3cd4-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="f3cd4-121">为 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 类或其中任何一个类的派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="f3cd4-122">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="f3cd4-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="f3cd4-123">提供 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 类或派生类的配置。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="f3cd4-124">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="f3cd4-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="f3cd4-125">提供 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 类或派生类的配置。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="f3cd4-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="f3cd4-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="f3cd4-127">提供 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 类或派生类的可选配置。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3cd4-128">父元素</span><span class="sxs-lookup"><span data-stu-id="f3cd4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f3cd4-129">元素</span><span class="sxs-lookup"><span data-stu-id="f3cd4-129">Element</span></span>|<span data-ttu-id="f3cd4-130">描述</span><span class="sxs-lookup"><span data-stu-id="f3cd4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3cd4-131">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="f3cd4-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="f3cd4-132">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3cd4-133">备注</span><span class="sxs-lookup"><span data-stu-id="f3cd4-133">Remarks</span></span>  
 <span data-ttu-id="f3cd4-134">`<add>` 元素可以采用单个子元素，该元素指定标记处理程序的配置。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="f3cd4-135">这取决于通过 `<add>` 元素的 `type` 特性引用的处理程序类是否为此功能提供支持。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="f3cd4-136">提供此功能的令牌处理程序类必须公开采用 <xref:System.Xml.XmlElement> 对象的构造函数。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="f3cd4-137">某些内置安全令牌处理程序类提供此功能。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="f3cd4-138">这些类 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>、<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>和 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f3cd4-139">标记处理程序集合只能包含任何给定类型的单个处理程序。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="f3cd4-140">这意味着，例如，如果要将派生自 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 类的处理程序添加到集合中，则必须先从集合中删除默认存在的 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="f3cd4-141">您可以使用[\<remove >](remove.md)元素从集合中删除单个处理程序，也可以使用[\<clear >](clear.md)元素从集合中移除所有处理程序。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="f3cd4-142">在处理程序上指定的设置会重写[\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)元素下的标记处理程序集合中指定的等效设置，以及在[\<identityConfiguration >](identityconfiguration.md)元素下的服务级别指定的设置。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cd4-143">示例</span><span class="sxs-lookup"><span data-stu-id="f3cd4-143">Example</span></span>  
 <span data-ttu-id="f3cd4-144">下面的 XML 演示了如何使用 `<add>` 和 `<remove>` 元素将默认会话标记处理程序替换为自定义会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="f3cd4-145">XML 取自 `ClaimsAwareWebFarm` 示例。</span><span class="sxs-lookup"><span data-stu-id="f3cd4-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
