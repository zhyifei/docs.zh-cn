---
title: "如何：使用 ASP.NET 成员资格提供程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 74056ae23b08850b9c9a564248d6e276fc518a8a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="d72b8-102">如何：使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="d72b8-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="d72b8-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 成员资格提供程序是一种功能，可供 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 开发人员用于创建允许用户创建唯一用户名和密码组合的网站。</span><span class="sxs-lookup"><span data-stu-id="d72b8-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="d72b8-104">使用此工具，任何用户都可以在该网站上建立帐户，并登录网站以便独占访问该网站及其服务。</span><span class="sxs-lookup"><span data-stu-id="d72b8-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="d72b8-105">这与要求用户在 Windows 域中具有帐户的 Windows 安全完全不同。</span><span class="sxs-lookup"><span data-stu-id="d72b8-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="d72b8-106">所有提供凭据（用户名/密码组合）的用户都可以使用该网站及其服务。</span><span class="sxs-lookup"><span data-stu-id="d72b8-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="d72b8-107">有关示例应用程序，请参阅[成员资格和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d72b8-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="d72b8-108">有关使用信息[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]角色提供程序功能，请参阅[如何： 使用 ASP.NET 角色提供程序与服务](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)。</span><span class="sxs-lookup"><span data-stu-id="d72b8-108">For information about using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="d72b8-109">成员资格功能要求使用 SQL Server 数据库来存储用户信息。</span><span class="sxs-lookup"><span data-stu-id="d72b8-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="d72b8-110">此功能还包括用于向忘记密码的用户提示问题的方法。</span><span class="sxs-lookup"><span data-stu-id="d72b8-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d72b8-111"> 开发人员可以出于安全目的利用这些功能。</span><span class="sxs-lookup"><span data-stu-id="d72b8-111"> developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="d72b8-112">当集成到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序中时，用户必须向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端应用程序提供用户名/密码组合。</span><span class="sxs-lookup"><span data-stu-id="d72b8-112">When integrated into an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="d72b8-113">若要将数据传输到[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务，请使用一个绑定，支持用户/密码凭据，如<xref:System.ServiceModel.WSHttpBinding>(在配置中， [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) 并设置客户端凭据类型转换为`UserName`。</span><span class="sxs-lookup"><span data-stu-id="d72b8-113">To transfer the data to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="d72b8-114">在服务上，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全基于用户名和密码对用户进行身份验证，还会分配由 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 角色指定的角色。</span><span class="sxs-lookup"><span data-stu-id="d72b8-114">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security authenticates the user based on the user name and password, and also assigns the role specified by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d72b8-115"> 不提供使用用户名/密码组合或其他用户信息填充数据库的方法。</span><span class="sxs-lookup"><span data-stu-id="d72b8-115"> does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="d72b8-116">配置成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="d72b8-116">To configure the membership provider</span></span>  
  
1.  <span data-ttu-id="d72b8-117">在 Web.config 文件中，在 <`system.web`> 元素，创建 <`membership`> 元素。</span><span class="sxs-lookup"><span data-stu-id="d72b8-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2.  <span data-ttu-id="d72b8-118">在 `<membership>` 元素之下创建一个 `<providers>` 元素。</span><span class="sxs-lookup"><span data-stu-id="d72b8-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3.  <span data-ttu-id="d72b8-119">为的子级 <`providers`> 元素中，添加`<clear />`元素以刷新提供程序的集合。</span><span class="sxs-lookup"><span data-stu-id="d72b8-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4.  <span data-ttu-id="d72b8-120">下`<clear />`元素，创建 <`add`> 元素具有以下属性设置为适当的值： `name`， `type`， `connectionStringName`， `applicationName`， `enablePasswordRetrieval`， `enablePasswordReset`， `requiresQuestionAndAnswer``requiresUniqueEmail`，和`passwordFormat`。</span><span class="sxs-lookup"><span data-stu-id="d72b8-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="d72b8-121">`name` 属性以后作为一个值在配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="d72b8-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="d72b8-122">下面的示例将其设置为 `SqlMembershipProvider`。</span><span class="sxs-lookup"><span data-stu-id="d72b8-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="d72b8-123">下面的示例显示配置节。</span><span class="sxs-lookup"><span data-stu-id="d72b8-123">The following example shows the configuration section.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="d72b8-124">配置服务安全以接受用户名/密码组合</span><span class="sxs-lookup"><span data-stu-id="d72b8-124">To configure service security to accept the user name/password combination</span></span>  
  
1.  <span data-ttu-id="d72b8-125">在配置文件中，在[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素中，添加[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d72b8-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2.  <span data-ttu-id="d72b8-126">添加[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)绑定部分。</span><span class="sxs-lookup"><span data-stu-id="d72b8-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d72b8-127">创建[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]绑定元素，请参阅[如何： 在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="d72b8-127"> creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3.  <span data-ttu-id="d72b8-128">将 `mode` 元素的 `<security>` 属性设置为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="d72b8-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4.  <span data-ttu-id="d72b8-129">设置`clientCredentialType`属性 <`message`> 元素`UserName`。</span><span class="sxs-lookup"><span data-stu-id="d72b8-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="d72b8-130">这将指定将用户名/密码对用作客户端的凭据。</span><span class="sxs-lookup"><span data-stu-id="d72b8-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="d72b8-131">下面的示例显示绑定的配置代码。</span><span class="sxs-lookup"><span data-stu-id="d72b8-131">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="d72b8-132">配置服务以使用成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="d72b8-132">To configure a service to use the membership provider</span></span>  
  
1.  <span data-ttu-id="d72b8-133">为的子级`<system.serviceModel>`元素中，添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素</span><span class="sxs-lookup"><span data-stu-id="d72b8-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2.  <span data-ttu-id="d72b8-134">添加[ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)到 <`behaviors`> 元素。</span><span class="sxs-lookup"><span data-stu-id="d72b8-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3.  <span data-ttu-id="d72b8-135">添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)并设置`name`属性设为适当的值。</span><span class="sxs-lookup"><span data-stu-id="d72b8-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="d72b8-136">添加[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)到 <`behavior`> 元素。</span><span class="sxs-lookup"><span data-stu-id="d72b8-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5.  <span data-ttu-id="d72b8-137">添加[ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)到`<serviceCredentials>`元素。</span><span class="sxs-lookup"><span data-stu-id="d72b8-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6.  <span data-ttu-id="d72b8-138">将 `userNamePasswordValidationMode` 属性设置为 `MembershipProvider`。</span><span class="sxs-lookup"><span data-stu-id="d72b8-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d72b8-139">如果未设置 `userNamePasswordValidationMode` 值，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将使用 Windows 身份验证代替 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 成员资格提供程序。</span><span class="sxs-lookup"><span data-stu-id="d72b8-139">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
7.  <span data-ttu-id="d72b8-140">将 `membershipProviderName` 属性设置为提供程序的名称（在本主题的第一个过程中添加提供程序时指定）。</span><span class="sxs-lookup"><span data-stu-id="d72b8-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="d72b8-141">下面的示例演示至此为止的 `<serviceCredentials>` 片段。</span><span class="sxs-lookup"><span data-stu-id="d72b8-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="d72b8-142">示例</span><span class="sxs-lookup"><span data-stu-id="d72b8-142">Example</span></span>  
 <span data-ttu-id="d72b8-143">下面的代码示例演示使用 ASP 成员资格功能的服务的配置。</span><span class="sxs-lookup"><span data-stu-id="d72b8-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d72b8-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d72b8-144">See Also</span></span>  
 [<span data-ttu-id="d72b8-145">如何： 与服务一起使用 ASP.NET 角色提供程序</span><span class="sxs-lookup"><span data-stu-id="d72b8-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="d72b8-146">成员资格和角色提供程序</span><span class="sxs-lookup"><span data-stu-id="d72b8-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
