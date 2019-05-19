---
title: 如何：将 ASP.NET 授权管理器角色提供程序与服务一起使用
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 778af929b4cfc96ce0683d304be5f8fb87a0e47b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880203"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>如何：将 ASP.NET 授权管理器角色提供程序与服务一起使用
当 ASP.NET 托管的 Web 服务时，您可以将授权管理器集成到应用程序以提供对服务的授权。 授权管理器允许应用程序开发人员定义各个操作，这些操作可组织在一起形成任务。 然后管理员可以授权角色执行特定任务或各个操作。 授权管理器提供管理工具，并将其作为 Microsoft 管理控制台 (MMC) 管理单元来管理角色、任务、操作和用户。 管理员在 XML 文件、Active Directory 或 Active Directory 应用程序模式 (ADAM) 存储区中配置授权管理器策略存储区。  
  
 授权管理器是通过配置授权管理器 ASP.NET 角色提供程序承载 Web 服务的 ASP.NET 应用程序集成到应用程序。 像其他 ASP.NET 角色提供程序，使用配置授权管理器 ASP.NET 角色提供程序 <`providers`> 元素。  
  
 下面的代码示例是 Web 服务配置文件的一部分，该 Web 服务将授权管理器集成到应用程序中。  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 有关如何将 ASP.NET 角色提供程序与 WCF 应用程序相集成的详细信息，请参阅[如何：与服务一起使用 ASP.NET 角色提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)。 有关使用授权管理器和 ASP.NET 的详细信息，请参阅[如何：使用授权管理器 (AzMan) 与 ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303)。  
  
## <a name="see-also"></a>请参阅

- [如何：与服务一起使用 ASP.NET 角色提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
