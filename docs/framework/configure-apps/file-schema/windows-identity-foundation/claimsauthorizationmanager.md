---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 06824e20286f8905ad3a8ac9d2b4a30366a6ec10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757367"
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="60406-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="60406-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="60406-103">注册用于传入声明的声明授权管理器。</span><span class="sxs-lookup"><span data-stu-id="60406-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="60406-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="60406-104">\<system.identityModel></span></span>  
<span data-ttu-id="60406-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="60406-105">\<identityConfiguration></span></span>  
<span data-ttu-id="60406-106">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="60406-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60406-107">语法</span><span class="sxs-lookup"><span data-stu-id="60406-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60406-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="60406-108">Attributes and Elements</span></span>  
 <span data-ttu-id="60406-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="60406-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60406-110">特性</span><span class="sxs-lookup"><span data-stu-id="60406-110">Attributes</span></span>  
  
|<span data-ttu-id="60406-111">特性</span><span class="sxs-lookup"><span data-stu-id="60406-111">Attribute</span></span>|<span data-ttu-id="60406-112">描述</span><span class="sxs-lookup"><span data-stu-id="60406-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60406-113">类型</span><span class="sxs-lookup"><span data-stu-id="60406-113">type</span></span>|<span data-ttu-id="60406-114">派生自的自定义类型<xref:System.Security.Claims.ClaimsAuthorizationManager>类。</span><span class="sxs-lookup"><span data-stu-id="60406-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="60406-115">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="60406-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60406-116">子元素</span><span class="sxs-lookup"><span data-stu-id="60406-116">Child Elements</span></span>  
 <span data-ttu-id="60406-117">如果没有任何`type`属性，或者如果`type`属性引用<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthorizationManager>`元素不采用子元素; 但是，类派生自<xref:System.Security.Claims.ClaimsAuthorizationManager>可以定义子配置元素。</span><span class="sxs-lookup"><span data-stu-id="60406-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60406-118">父元素</span><span class="sxs-lookup"><span data-stu-id="60406-118">Parent Elements</span></span>  
  
|<span data-ttu-id="60406-119">元素</span><span class="sxs-lookup"><span data-stu-id="60406-119">Element</span></span>|<span data-ttu-id="60406-120">描述</span><span class="sxs-lookup"><span data-stu-id="60406-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60406-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="60406-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="60406-122">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="60406-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60406-123">备注</span><span class="sxs-lookup"><span data-stu-id="60406-123">Remarks</span></span>  
 <span data-ttu-id="60406-124">通过提供的默认行为<xref:System.Security.Claims.ClaimsAuthorizationManager>类始终授权的传入声明。</span><span class="sxs-lookup"><span data-stu-id="60406-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="60406-125">如果没有`type`指定属性或如果`type`属性指定<xref:System.Security.Claims.ClaimsAuthorizationManager>类，`<claimsAuthorizationManager>`元素不采用子元素。</span><span class="sxs-lookup"><span data-stu-id="60406-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="60406-126">你可以指定`type`特性来注册类型派生自<xref:System.Security.Claims.ClaimsAuthorizationManager>类，以实现自定义行为。</span><span class="sxs-lookup"><span data-stu-id="60406-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="60406-127">派生的类可以支持的子元素通过配置`<claimsAuthorizationManager>`通过重写元素<xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A>方法以处理这些元素。</span><span class="sxs-lookup"><span data-stu-id="60406-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="60406-128">为子元素定义的架构是最多的类设计器。</span><span class="sxs-lookup"><span data-stu-id="60406-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="60406-129">使用时<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>或<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>类提供在代码中，引用的标识配置的基于声明的访问控制`<federationConfiguration>`元素会配置的声明授权管理器和用于使的策略授权决策。</span><span class="sxs-lookup"><span data-stu-id="60406-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="60406-130">这是为 true，即使在不是被动 Web 方案，例如 Windows Communication Foundation (WCF) 应用程序或不是基于 Web 的应用程序的方案中。</span><span class="sxs-lookup"><span data-stu-id="60406-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="60406-131">如果应用程序不是被动的 Web 应用程序，`<claimsAuthorizationManager>`元素 （和其子策略元素，如果存在） 的引用的标识配置的应用的唯一设置。</span><span class="sxs-lookup"><span data-stu-id="60406-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="60406-132">将忽略所有其他设置。</span><span class="sxs-lookup"><span data-stu-id="60406-132">All other settings are ignored.</span></span> <span data-ttu-id="60406-133">有关详细信息，请参阅[ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="60406-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="60406-134">此元素设置<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="60406-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60406-135">示例</span><span class="sxs-lookup"><span data-stu-id="60406-135">Example</span></span>  
 <span data-ttu-id="60406-136">下面的 XML 演示声明授权的配置管理器实现策略组成资源操作对其中每个指定的请求者必须具有对资源执行操作的声明的 boolean 类型的值组合。</span><span class="sxs-lookup"><span data-stu-id="60406-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="60406-137">实现声明授权管理器能够使用此策略的代码可在`ClaimsBasedAuthorization`示例。</span><span class="sxs-lookup"><span data-stu-id="60406-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
