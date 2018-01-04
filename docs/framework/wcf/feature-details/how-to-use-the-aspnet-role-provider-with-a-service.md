---
title: "如何：将 ASP.NET 角色提供程序与服务一起使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef526ed1f809fad2f07b66629bbc80530b764d65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="a79dd-102">如何：将 ASP.NET 角色提供程序与服务一起使用</span><span class="sxs-lookup"><span data-stu-id="a79dd-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="a79dd-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 角色提供程序（与 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 成员资格提供程序一起提供）是一种可供 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 开发人员创建网站的功能，这些网站允许用户通过网站创建帐户并向用户分配用于授权的角色。</span><span class="sxs-lookup"><span data-stu-id="a79dd-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="a79dd-104">借助此功能，任何用户都可以通过网站建立帐户，并登录以获取该网站及其服务的独占访问权。</span><span class="sxs-lookup"><span data-stu-id="a79dd-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="a79dd-105">这与要求用户在 Windows 域中具有帐户的 Windows 安全完全不同。</span><span class="sxs-lookup"><span data-stu-id="a79dd-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="a79dd-106">所有提供凭据（用户名/密码组合）的用户都可以使用该站点及其服务。</span><span class="sxs-lookup"><span data-stu-id="a79dd-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="a79dd-107">有关示例应用程序，请参阅[成员资格和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="a79dd-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a79dd-108">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]成员资格提供程序功能，请参阅[如何： 使用 ASP.NET 成员资格提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="a79dd-108"> the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="a79dd-109">角色提供程序功能使用 SQL Server 数据库存储用户信息。</span><span class="sxs-lookup"><span data-stu-id="a79dd-109">The role provider feature uses a SQL Server database to store user information.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a79dd-110"> 开发人员可以出于安全目的利用这些功能。</span><span class="sxs-lookup"><span data-stu-id="a79dd-110"> developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="a79dd-111">当集成到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序中时，用户必须向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端应用程序提供用户名/密码组合。</span><span class="sxs-lookup"><span data-stu-id="a79dd-111">When integrated into a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="a79dd-112">若要让 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 使用该数据库，您必须创建 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 类的一个实例，将其 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> 属性设置为 <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>，并将行为集合的实例添加到承载服务的 <xref:System.ServiceModel.ServiceHost> 中。</span><span class="sxs-lookup"><span data-stu-id="a79dd-112">To enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="a79dd-113">配置角色提供程序</span><span class="sxs-lookup"><span data-stu-id="a79dd-113">To configure the role provider</span></span>  
  
1.  <span data-ttu-id="a79dd-114">在 Web.config 文件中，在 <`system.web`> 元素中，添加 <`roleManager`> 元素，并设置其`enabled`属性设为`true`。</span><span class="sxs-lookup"><span data-stu-id="a79dd-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2.  <span data-ttu-id="a79dd-115">将 `defaultProvider` 属性设置为 `SqlRoleProvider`。</span><span class="sxs-lookup"><span data-stu-id="a79dd-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3.  <span data-ttu-id="a79dd-116">为的子级 <`roleManager`> 元素中，添加 <`providers`> 元素。</span><span class="sxs-lookup"><span data-stu-id="a79dd-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4.  <span data-ttu-id="a79dd-117">为的子级 <`providers`> 元素中，添加 <`add`> 元素具有以下属性设置为适当的值： `name`， `type`， `connectionStringName`，和`applicationName`，下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a79dd-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="a79dd-118">将服务配置为使用角色提供程序</span><span class="sxs-lookup"><span data-stu-id="a79dd-118">To configure the service to use the role provider</span></span>  
  
1.  <span data-ttu-id="a79dd-119">在 Web.config 文件中，添加[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a79dd-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="a79dd-120">添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素 <`system.ServiceModel`> 元素。</span><span class="sxs-lookup"><span data-stu-id="a79dd-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3.  <span data-ttu-id="a79dd-121">添加[ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)到 <`behaviors`> 元素。</span><span class="sxs-lookup"><span data-stu-id="a79dd-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4.  <span data-ttu-id="a79dd-122">添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)元素，并设置`name`属性设为适当的值。</span><span class="sxs-lookup"><span data-stu-id="a79dd-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5.  <span data-ttu-id="a79dd-123">添加[ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)到 <`behavior`> 元素。</span><span class="sxs-lookup"><span data-stu-id="a79dd-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6.  <span data-ttu-id="a79dd-124">将 `principalPermissionMode` 属性设置为 `UseAspNetRoles`。</span><span class="sxs-lookup"><span data-stu-id="a79dd-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7.  <span data-ttu-id="a79dd-125">将 `roleProviderName` 属性设置为 `SqlRoleProvider`。</span><span class="sxs-lookup"><span data-stu-id="a79dd-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="a79dd-126">下面的示例演示此配置的一个片段。</span><span class="sxs-lookup"><span data-stu-id="a79dd-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a79dd-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a79dd-127">See Also</span></span>  
 [<span data-ttu-id="a79dd-128">成员资格和角色提供程序</span><span class="sxs-lookup"><span data-stu-id="a79dd-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [<span data-ttu-id="a79dd-129">如何：使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="a79dd-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
