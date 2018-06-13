---
title: System.Web.Routing 集成
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 5bd405d66dcad597bbe6f452703d25372fdb7682
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498018"
---
# <a name="systemwebrouting-integration"></a>System.Web.Routing 集成
承载 Windows Communication Foundation (WCF) 服务在 Internet 信息服务 (IIS) 时你将一个.svc 文件放在该虚拟目录。 此 .svc 文件指定所用的服务主机工厂以及实现服务的类。 向服务发出请求时你的.svc 文件在 URI 中指定，例如： http://contoso.com/EmployeeServce.svc。 对于编写 REST 服务的程序员，此类型的 URI 并非最佳选择。 REST 服务的 URI 指定了特定资源，通常没有任何扩展。 <xref:System.Web.Routing>集成功能可用于承载响应无扩展的 Uri 的 WCF REST 服务。 有关路由，请参阅详细信息[ASP.NET 路由](http://go.microsoft.com/fwlink/?LinkId=184660)和[AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md)示例。  
  
## <a name="using-systemwebrouting-integration"></a>使用 System.Web.Routing 集成  
 若要使用 <xref:System.Web.Routing> 集成功能，请使用 <xref:System.ServiceModel.Activation.ServiceRoute> 类创建一个或多个路由，然后将这些路由添加到 Global.asax 文件中的 <xref:System.Web.Routing.RouteTable>。 这些路由可指定服务所响应的相对 URI。 下面的示例演示如何执行此操作。  
  
```  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));   
   }  
</script>  
```  
  
 这示例将具有以 Customers 开头的相对 URI 的所有请求路由到 `Service` 服务。  
  
 在 Web.config 文件中，必须添加 `System.Web.Routing.UrlRoutingModule` 模块，将 `runAllManagedModulesForAllRequests` 特性设置为 `true`，以及将 `UrlRoutingHandler` 处理程序添加到 `<system.webServer>` 元素，如下面的示例所示。  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 此示例将加载路由所需的模块和处理程序。 有关详细信息，请参阅[路由](../../../../docs/framework/wcf/feature-details/routing.md)。 另外，还必须在 `aspNetCompatibilityEnabled` 元素中将 `true` 特性设置为 `<serviceHostingEnvironment>`，如下面的示例所示。  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 实现该服务的类必须启用 ASP.NET 兼容性需求，如下面的示例所示。  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>请参阅  
 [WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [ASP.NET 路由](http://go.microsoft.com/fwlink/?LinkId=184660)
