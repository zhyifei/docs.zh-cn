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
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>如何：将 ASP.NET 角色提供程序与服务一起使用

ASP.NET角色提供程序（与ASP.NET成员提供程序结合）是一项功能，它使ASP.NET开发人员能够创建网站，允许用户使用网站创建帐户，并为授权目的分配角色。 借助此功能，任何用户都可以通过网站建立帐户，并登录以获取该网站及其服务的独占访问权。 这与要求用户在 Windows 域中具有帐户的 Windows 安全完全不同。 相反，任何提供其凭据（用户名/密码组合）的用户都可以使用该网站及其服务。  
  
有关示例应用程序，请参阅[成员资格和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)。 有关ASP.NET成员资格提供程序功能的详细信息，请参阅[：使用ASP.NET成员资格提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)。  
  
角色提供程序功能使用 SQL Server 数据库存储用户信息。 出于安全目的，Windows 通信基础 （WCF） 开发人员可以利用这些功能。 集成到 WCF 应用程序时，用户必须向 WCF 客户端应用程序提供用户名和密码组合。 要使 WCF 能够使用数据库，必须<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>创建类的实例，将其<xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>属性设置为<xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>，并将实例添加到承载服务<xref:System.ServiceModel.ServiceHost>的行为集合中。  
  
## <a name="configure-the-role-provider"></a>配置角色提供程序  
  
1. 在 Web.config 文件中`system.web`，在<>元素下，添加<>`roleManager`元素并将其`enabled`属性设置为 。 `true`  
  
2. 将 `defaultProvider` 属性设置为 `SqlRoleProvider`。  
  
3. 作为<>`roleManager`元素的子元素，添加<>`providers`元素。  
  
4. `providers`作为<>元素的子元素，添加一个<>`add`元素，其中将以下属性设置为适当的值： `name` `type`、`connectionStringName`和`applicationName`， 如以下示例所示。  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>将服务配置为使用角色提供程序  
  
1. 在 Web.config 文件中，添加[\<一个系统.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素。  
  
2. 将[\<行为>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素添加到<>`system.ServiceModel`元素。  
  
3. 向`behaviors`[\<<>元素添加服务行为>。](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)  
  
4. >元素添加[\<行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)并将`name`属性设置为适当的值。  
  
5. 将[\<服务授权>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)添加到<>`behavior`元素。  
  
6. 将 `principalPermissionMode` 属性设置为 `UseAspNetRoles`。  
  
7. 将 `roleProviderName` 属性设置为 `SqlRoleProvider`。 下面的示例演示此配置的一个片段。  
  
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
  
## <a name="see-also"></a>另请参阅

- [成员资格和角色提供程序](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [如何：使用 ASP.NET 成员资格提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
