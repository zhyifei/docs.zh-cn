---
title: 如何：使用 ASP.NET 成员资格提供程序
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: b86287440b2265349b853265f12a2f6e48b4cff3
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045272"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a>如何：使用 ASP.NET 成员资格提供程序

ASP.NET 成员资格提供程序是一项功能, 使 ASP.NET 开发人员能够创建允许用户创建唯一的用户名和密码组合的网站。 使用此工具，任何用户都可以在该网站上建立帐户，并登录网站以便独占访问该网站及其服务。 这与要求用户在 Windows 域中具有帐户的 Windows 安全完全不同。 所有提供凭据（用户名/密码组合）的用户都可以使用该网站及其服务。

有关示例应用程序, 请参阅[成员身份和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)。 有关使用 ASP.NET 角色提供程序功能的信息, 请[参阅如何:将 ASP.NET 角色提供程序用于服务](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)。

成员资格功能要求使用 SQL Server 数据库来存储用户信息。 此功能还包括用于向忘记密码的用户提示问题的方法。

Windows Communication Foundation (WCF) 开发人员可以出于安全目的利用这些功能。 当集成到 WCF 应用程序中时, 用户必须为 WCF 客户端应用程序提供用户名/密码组合。 若要将数据传输到 WCF 服务, 请使用支持用户名/密码凭据的绑定, 如<xref:System.ServiceModel.WSHttpBinding> (在配置中为[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)), 并将客户端凭据类型设置为。 `UserName` 在服务上, WCF 安全根据用户名和密码对用户进行身份验证, 并分配由 ASP.NET 角色指定的角色。

> [!NOTE]
> WCF 不提供用用户名/密码组合或其他用户信息填充数据库的方法。

### <a name="to-configure-the-membership-provider"></a>配置成员资格提供程序

1. 在 web.config 文件中的 <`system.web`> 元素下, 创建一个 <`membership`> 元素。

2. 在 `<membership>`<providers> 元素之下创建一个`<providers>` 元素。

3. 添加元素以刷新提供程序`providers`的集合, 作为 < > 元素的子元素。 `<clear />`

4. `connectionStringName` `type` `add` `name` `enablePasswordReset` `applicationName` `requiresQuestionAndAnswer` `enablePasswordRetrieval`在元素下, 创建一个 < > 元素, 并将以下属性设置为适当的值:、、、、、、 `<clear />`、 `requiresUniqueEmail`和。`passwordFormat` `name` 属性以后作为一个值在配置文件中使用。 下面的示例将其设置为 `SqlMembershipProvider`。

    下面的示例显示配置节。

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

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a>配置服务安全以接受用户名/密码组合

1. 在配置文件中的[ \<system.servicemodel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素下, 添加绑定 > 元素。

2. 将 wsHttpBinding [ >添加到"绑定"部分。\<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 有关创建 WCF 绑定元素的详细信息, 请参阅[如何:在配置](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)中指定服务绑定。

3. 将 `mode` 元素的 `<security>` 属性设置为 `Message`。

4. `UserName`将 <`message`> 元素的`clientCredentialType`特性设置为。 这将指定将用户名/密码对用作客户端的凭据。

    下面的示例显示绑定的配置代码。

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

### <a name="to-configure-a-service-to-use-the-membership-provider"></a>配置服务以使用成员资格提供程序

1. 作为`<system.serviceModel>`元素的子元素, [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素添加行为

2. `behaviors` [将\<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)添加到 < > 元素。

3. > 中添加一个[ \<行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md), 并`name`将特性设置为适当的值。

4. `behavior` [将\<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)添加到 < > 元素。

5. 将 userNameAuthentication > 添加到元素。`<serviceCredentials>` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)

6. 将 `userNamePasswordValidationMode` 属性设置为 `MembershipProvider`。

    > [!IMPORTANT]
    > 如果未`userNamePasswordValidationMode`设置此值, WCF 将使用 Windows 身份验证而不是 ASP.NET 成员资格提供程序。

7. 将 `membershipProviderName` 属性设置为提供程序的名称（在本主题的第一个过程中添加提供程序时指定）。 下面的示例演示至此为止的 `<serviceCredentials>` 片段。

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

## <a name="example"></a>示例

下面的代码示例演示使用 ASP 成员资格功能的服务的配置。

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

## <a name="see-also"></a>请参阅

- [如何：将 ASP.NET 角色提供程序与服务一起使用](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [成员资格和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
