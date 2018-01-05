---
title: "如何：将 ASP.NET Web 服务代码迁移到 Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e56d2481785a9a8486174e611001b9d800c7c869
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a>如何：将 ASP.NET Web 服务代码迁移到 Windows Communication Foundation
下面的过程描述如何将 ASP.NET Web 服务迁移到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a>将 ASP.NET Web 服务代码迁移到 WCF  
  
1.  确保该服务存在一组综合测试。  
  
2.  为该服务生成 WSDL，并将一个副本保存在服务的 .asmx 文件所在的文件夹中。  
  
3.  升级 ASP.NET Web 服务以使用 .NET 2.0。 首先将.NET Framework 2.0 部署到在 IIS 中，应用程序，然后使用 Visual Studio 2005 来自动化代码转换过程中，如中所述[分步指南将 Web 项目从 Visual Studio.NET 2002年/2003 到 Visual Studio2005](http://go.microsoft.com/fwlink/?LinkId=96492)。 运行测试集。  
  
4.  为 `Namespace` 属性的 `Name` 和 <xref:System.Web.Services.WebService> 参数提供明确的值（如果尚未提供）。 为 `MessageName` 的 <xref:System.Web.Services.WebMethodAttribute> 参数执行同样的操作。 如果尚未为 SOAPAction HTTP 头（请求是通过此 HTTP 头路由到方法的）提供明确的值，则利用 `Action` 显式指定 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 参数的默认值。  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
5.  测试更改。  
  
6.  将类的方法体中任何独立存在的代码移到要使用原始类的单独的类中。  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
    }  
  
    internal class ActualAdder  
    {  
         internal double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
7.  测试更改。  
  
8.  将对 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 程序集 System.ServiceModel 和 System.Runtime.Serialization 的引用添加到 ASP.NET Web 服务项目。  
  
9. 运行[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]从 WSDL 的客户端类。 将生成的类模块添加到解决方案。  
  
10. 前面的步骤中生成的类模块包含接口定义。  
  
    ```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface AdderSoap  
    {  
         [System.ServiceModel.OperationContractAttribute(  
          Action="http://tempuri.org/Add",   
          ReplyAction="http://tempuri.org/Add")]  
         AddResponse Add(AddRequest request);  
    }  
    ```  
  
     修改 ASP.NET Web 服务类的定义，这样该类可以定义为实现该接口，如下面的示例代码中所示。  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder: AdderSoap  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
            return new AddResponse(  
            new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
11. 编译该项目。 由于在步骤 9 中生成的代码与某些类型定义重复，所以可能存在一些错误。 一般通过删除这些预先存在的类型定义来修复这些错误。 测试更改。  
  
12. 移除 ASP.NET 特定的属性，如 <xref:System.Web.Services.WebService>、<xref:System.Web.Services.WebMethodAttribute> 和 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>。  
  
    ```  
    public class Adder: AdderSoap  
    {  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
              return new AddResponse(  
             new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
13. 配置类（现在为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务类型）以要求使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET 兼容模式，前提是 ASP.NET Web 服务依赖下列任意项：  
  
    -   <xref:System.Web.HttpContext> 类。  
  
    -   ASP.NET 配置文件。  
  
    -   .asmx 文件上的 ACL。  
  
    -   IIS 身份验证选项。  
  
    -   ASP.NET 模拟选项。  
  
    -   ASP.NET 全球化。  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. 将原始 .asmx 文件重命名为 .asmx.old。  
  
15. 为服务创建一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务文件，为该文件指定扩展名 .asmx，然后将其保存到 IIS 中的应用程序根目录中。  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. 将服务的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 配置添加到其 Web.config 文件中。 配置服务以使用[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)，若要使用在前面的步骤中，创建扩展名为.asmx 服务文件和不为其自身，生成的 WSDL 但若要使用第 2 步中从 WSDL。 另外，还要将其配置为使用 ASP.NET 兼容模式（如果需要）。  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.web>  
      <compilation>  
      <buildProviders>  
       <remove extension=".asmx" />  
       <add extension=".asmx"   
        type=  
        "System.ServiceModel.Activation.ServiceBuildProvider,  
        T:System.ServiceModel, Version=2.0.0.0,   
       Culture=neutral,   
       PublicKeyToken=b77a5c561934e089" />  
      </buildProviders>  
      </compilation>  
     </system.web>  
     <system.serviceModel>  
      <services>  
      <service name="MyOrganization.Adder "  
        behaviorConfiguration="AdderBehavior">  
       <endpoint   
        address=""  
        binding="basicHttpBinding"  
        contract="AdderSoap "/>  
       </service>  
      </services>  
      <behaviors>  
      <behavior name="AdderBehavior">  
       <metadataPublishing   
        enableMetadataExchange="true"   
        enableGetWsdl="true"   
        enableHelpPage="true"   
        metadataLocation=  
        "http://MyHost.com/AdderService/Service.WSDL"/>  
      </behavior>  
      </behaviors>  
      <serviceHostingEnvironment   
       aspNetCompatibilityEnabled ="true"/>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
17. 保存该配置。  
  
18. 编译该项目。  
  
19. 运行该测试集以确定所有更改均已生效。  
  
## <a name="see-also"></a>请参阅  
 [如何：将 ASP.NET Web 服务客户端代码迁移到 Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
