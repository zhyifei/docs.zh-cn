---
title: 如何：将 ASP.NET 角色提供程序与服务一起使用
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184774"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="d88ae-102">如何：将 ASP.NET 角色提供程序与服务一起使用</span><span class="sxs-lookup"><span data-stu-id="d88ae-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="d88ae-103">ASP.NET角色提供程序（与ASP.NET成员提供程序结合）是一项功能，它使ASP.NET开发人员能够创建网站，允许用户使用网站创建帐户，并为授权目的分配角色。</span><span class="sxs-lookup"><span data-stu-id="d88ae-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="d88ae-104">借助此功能，任何用户都可以通过网站建立帐户，并登录以获取该网站及其服务的独占访问权。</span><span class="sxs-lookup"><span data-stu-id="d88ae-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="d88ae-105">这与要求用户在 Windows 域中具有帐户的 Windows 安全完全不同。</span><span class="sxs-lookup"><span data-stu-id="d88ae-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="d88ae-106">相反，任何提供其凭据（用户名/密码组合）的用户都可以使用该网站及其服务。</span><span class="sxs-lookup"><span data-stu-id="d88ae-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="d88ae-107">有关示例应用程序，请参阅[成员资格和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="d88ae-108">有关ASP.NET成员资格提供程序功能的详细信息，请参阅[：使用ASP.NET成员资格提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="d88ae-109">角色提供程序功能使用 SQL Server 数据库存储用户信息。</span><span class="sxs-lookup"><span data-stu-id="d88ae-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="d88ae-110">出于安全目的，Windows 通信基础 （WCF） 开发人员可以利用这些功能。</span><span class="sxs-lookup"><span data-stu-id="d88ae-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="d88ae-111">集成到 WCF 应用程序时，用户必须向 WCF 客户端应用程序提供用户名和密码组合。</span><span class="sxs-lookup"><span data-stu-id="d88ae-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="d88ae-112">要使 WCF 能够使用数据库，必须<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>创建类的实例，将其<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>属性设置为<xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>，并将实例添加到承载服务<xref:System.ServiceModel.ServiceHost>的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="d88ae-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="d88ae-113">配置角色提供程序</span><span class="sxs-lookup"><span data-stu-id="d88ae-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="d88ae-114">在 Web.config 文件中`system.web`，在<>元素下，添加<>`roleManager`元素并将其`enabled`属性设置为 。 `true`</span><span class="sxs-lookup"><span data-stu-id="d88ae-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="d88ae-115">将 `defaultProvider` 属性设置为 `SqlRoleProvider`。</span><span class="sxs-lookup"><span data-stu-id="d88ae-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="d88ae-116">作为<>`roleManager`元素的子元素，添加<>`providers`元素。</span><span class="sxs-lookup"><span data-stu-id="d88ae-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="d88ae-117">`providers`作为<>元素的子元素，添加一个<>`add`元素，其中将以下属性设置为适当的值： `name` `type`、`connectionStringName`和`applicationName`， 如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d88ae-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="d88ae-118">将服务配置为使用角色提供程序</span><span class="sxs-lookup"><span data-stu-id="d88ae-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="d88ae-119">在 Web.config 文件中，添加[\<一个系统.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d88ae-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="d88ae-120">将[\<行为>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素添加到<>`system.ServiceModel`元素。</span><span class="sxs-lookup"><span data-stu-id="d88ae-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="d88ae-121">向`behaviors`[\<<>元素添加服务行为>。](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d88ae-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="d88ae-122">>元素添加[\<行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)并将`name`属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="d88ae-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="d88ae-123">将[\<服务授权>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)添加到<>`behavior`元素。</span><span class="sxs-lookup"><span data-stu-id="d88ae-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="d88ae-124">将 `principalPermissionMode` 属性设置为 `UseAspNetRoles`。</span><span class="sxs-lookup"><span data-stu-id="d88ae-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="d88ae-125">将 `roleProviderName` 属性设置为 `SqlRoleProvider`。</span><span class="sxs-lookup"><span data-stu-id="d88ae-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="d88ae-126">下面的示例演示此配置的一个片段。</span><span class="sxs-lookup"><span data-stu-id="d88ae-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d88ae-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d88ae-127">See also</span></span>

- [<span data-ttu-id="d88ae-128">成员资格和角色提供程序</span><span class="sxs-lookup"><span data-stu-id="d88ae-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="d88ae-129">如何：使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="d88ae-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
