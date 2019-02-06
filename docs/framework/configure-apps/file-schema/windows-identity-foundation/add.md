---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 34643d10ef1ed2e87152e5013634e62859e0594e
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759478"
---
# <a name="add"></a><span data-ttu-id="db3e0-101">\<add></span><span class="sxs-lookup"><span data-stu-id="db3e0-101">\<add></span></span>
<span data-ttu-id="db3e0-102">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="db3e0-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="db3e0-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="db3e0-103">\<system.identityModel></span></span>  
<span data-ttu-id="db3e0-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="db3e0-104">\<identityConfiguration></span></span>  
<span data-ttu-id="db3e0-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="db3e0-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="db3e0-106">\<add></span><span class="sxs-lookup"><span data-stu-id="db3e0-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db3e0-107">语法</span><span class="sxs-lookup"><span data-stu-id="db3e0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db3e0-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="db3e0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="db3e0-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="db3e0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db3e0-110">特性</span><span class="sxs-lookup"><span data-stu-id="db3e0-110">Attributes</span></span>  
  
|<span data-ttu-id="db3e0-111">特性</span><span class="sxs-lookup"><span data-stu-id="db3e0-111">Attribute</span></span>|<span data-ttu-id="db3e0-112">描述</span><span class="sxs-lookup"><span data-stu-id="db3e0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db3e0-113">类型</span><span class="sxs-lookup"><span data-stu-id="db3e0-113">type</span></span>|<span data-ttu-id="db3e0-114">令牌处理程序要添加的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="db3e0-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="db3e0-115">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)。</span><span class="sxs-lookup"><span data-stu-id="db3e0-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db3e0-116">子元素</span><span class="sxs-lookup"><span data-stu-id="db3e0-116">Child Elements</span></span>  
  
|<span data-ttu-id="db3e0-117">元素</span><span class="sxs-lookup"><span data-stu-id="db3e0-117">Element</span></span>|<span data-ttu-id="db3e0-118">描述</span><span class="sxs-lookup"><span data-stu-id="db3e0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db3e0-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="db3e0-119">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="db3e0-120">提供用于配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类的任何一个的派生的类。</span><span class="sxs-lookup"><span data-stu-id="db3e0-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="db3e0-121">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="db3e0-121">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="db3e0-122">提供配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="db3e0-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="db3e0-123">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="db3e0-123">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="db3e0-124">提供配置<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="db3e0-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="db3e0-125">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="db3e0-125">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="db3e0-126">提供的可选配置<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="db3e0-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db3e0-127">父元素</span><span class="sxs-lookup"><span data-stu-id="db3e0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="db3e0-128">元素</span><span class="sxs-lookup"><span data-stu-id="db3e0-128">Element</span></span>|<span data-ttu-id="db3e0-129">描述</span><span class="sxs-lookup"><span data-stu-id="db3e0-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db3e0-130">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="db3e0-130">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="db3e0-131">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="db3e0-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db3e0-132">备注</span><span class="sxs-lookup"><span data-stu-id="db3e0-132">Remarks</span></span>  
 <span data-ttu-id="db3e0-133">`<add>`元素可能需要指定的标记处理程序的配置的单个子元素。</span><span class="sxs-lookup"><span data-stu-id="db3e0-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="db3e0-134">这是依赖于处理程序类是否通过引用`type`属性的`<add>`元素提供了此功能的支持。</span><span class="sxs-lookup"><span data-stu-id="db3e0-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="db3e0-135">提供此功能的标记处理程序类必须公开一个构造函数采用<xref:System.Xml.XmlElement>对象。</span><span class="sxs-lookup"><span data-stu-id="db3e0-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="db3e0-136">多个内置的安全令牌处理程序类并提供此功能。</span><span class="sxs-lookup"><span data-stu-id="db3e0-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="db3e0-137">这些类是<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="db3e0-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db3e0-138">标记处理程序集合只能包含单个处理任何的程序给定的类型。</span><span class="sxs-lookup"><span data-stu-id="db3e0-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="db3e0-139">这意味着，例如，如果你想要添加的处理程序派生自<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类到集合中，您必须首先删除<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>，这是默认情况下，集合中存在。</span><span class="sxs-lookup"><span data-stu-id="db3e0-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="db3e0-140">可以使用[\<删除 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)要从集合或使用删除单个处理程序元素[\<清除 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)要从集合中移除所有处理程序元素。</span><span class="sxs-lookup"><span data-stu-id="db3e0-140">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="db3e0-141">上一个处理程序指定设置重写下的标记处理程序集合中指定的等效设置[ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)元素，并在服务级别下指定的[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="db3e0-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db3e0-142">示例</span><span class="sxs-lookup"><span data-stu-id="db3e0-142">Example</span></span>  
 <span data-ttu-id="db3e0-143">下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="db3e0-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="db3e0-144">XML 来自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="db3e0-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
