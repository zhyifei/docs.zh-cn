---
title: '&lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 4cd86a858223997ed379d2b26518e14f6d3ebb3e
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48037198"
---
# <a name="ltaddgt"></a><span data-ttu-id="b2be0-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="b2be0-102">&lt;add&gt;</span></span>
<span data-ttu-id="b2be0-103">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="b2be0-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="b2be0-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b2be0-104">\<system.identityModel></span></span>  
<span data-ttu-id="b2be0-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b2be0-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b2be0-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b2be0-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b2be0-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b2be0-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2be0-108">语法</span><span class="sxs-lookup"><span data-stu-id="b2be0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2be0-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b2be0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2be0-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b2be0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2be0-111">特性</span><span class="sxs-lookup"><span data-stu-id="b2be0-111">Attributes</span></span>  
  
|<span data-ttu-id="b2be0-112">特性</span><span class="sxs-lookup"><span data-stu-id="b2be0-112">Attribute</span></span>|<span data-ttu-id="b2be0-113">描述</span><span class="sxs-lookup"><span data-stu-id="b2be0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2be0-114">类型</span><span class="sxs-lookup"><span data-stu-id="b2be0-114">type</span></span>|<span data-ttu-id="b2be0-115">令牌处理程序要添加的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="b2be0-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="b2be0-116">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24)。</span><span class="sxs-lookup"><span data-stu-id="b2be0-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2be0-117">子元素</span><span class="sxs-lookup"><span data-stu-id="b2be0-117">Child Elements</span></span>  
  
|<span data-ttu-id="b2be0-118">元素</span><span class="sxs-lookup"><span data-stu-id="b2be0-118">Element</span></span>|<span data-ttu-id="b2be0-119">描述</span><span class="sxs-lookup"><span data-stu-id="b2be0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2be0-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b2be0-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="b2be0-121">提供用于配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类的任何一个的派生的类。</span><span class="sxs-lookup"><span data-stu-id="b2be0-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="b2be0-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b2be0-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="b2be0-123">提供配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="b2be0-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="b2be0-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="b2be0-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="b2be0-125">提供配置<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="b2be0-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="b2be0-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="b2be0-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="b2be0-127">提供的可选配置<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="b2be0-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2be0-128">父元素</span><span class="sxs-lookup"><span data-stu-id="b2be0-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b2be0-129">元素</span><span class="sxs-lookup"><span data-stu-id="b2be0-129">Element</span></span>|<span data-ttu-id="b2be0-130">描述</span><span class="sxs-lookup"><span data-stu-id="b2be0-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2be0-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b2be0-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="b2be0-132">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="b2be0-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2be0-133">备注</span><span class="sxs-lookup"><span data-stu-id="b2be0-133">Remarks</span></span>  
 <span data-ttu-id="b2be0-134">`<add>`元素可能需要指定的标记处理程序的配置的单个子元素。</span><span class="sxs-lookup"><span data-stu-id="b2be0-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="b2be0-135">这是依赖于处理程序类是否通过引用`type`属性的`<add>`元素提供了此功能的支持。</span><span class="sxs-lookup"><span data-stu-id="b2be0-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="b2be0-136">提供此功能的标记处理程序类必须公开一个构造函数采用<xref:System.Xml.XmlElement>对象。</span><span class="sxs-lookup"><span data-stu-id="b2be0-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="b2be0-137">多个内置的安全令牌处理程序类并提供此功能。</span><span class="sxs-lookup"><span data-stu-id="b2be0-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="b2be0-138">这些类是<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="b2be0-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b2be0-139">标记处理程序集合只能包含单个处理任何的程序给定的类型。</span><span class="sxs-lookup"><span data-stu-id="b2be0-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="b2be0-140">这意味着，例如，如果你想要添加的处理程序派生自<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类到集合中，您必须首先删除<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>，这是默认情况下，集合中存在。</span><span class="sxs-lookup"><span data-stu-id="b2be0-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="b2be0-141">可以使用[\<删除 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)要从集合或使用删除单个处理程序元素[\<清除 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)要从集合中移除所有处理程序元素。</span><span class="sxs-lookup"><span data-stu-id="b2be0-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="b2be0-142">上一个处理程序指定设置重写下的标记处理程序集合中指定的等效设置[ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)元素，并在服务级别下指定的[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="b2be0-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2be0-143">示例</span><span class="sxs-lookup"><span data-stu-id="b2be0-143">Example</span></span>  
 <span data-ttu-id="b2be0-144">下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="b2be0-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="b2be0-145">XML 来自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="b2be0-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
