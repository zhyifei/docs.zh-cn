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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 94d6cc499caddc8b3cbbf8ba7845e4de5441165c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="813dd-102">如何：将 ASP.NET Web 服务代码迁移到 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="813dd-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="813dd-103">下面的过程描述如何将 ASP.NET Web 服务迁移到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="813dd-103">The following procedure describes how to migrate an ASP.NET Web Service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="813dd-104">过程</span><span class="sxs-lookup"><span data-stu-id="813dd-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="813dd-105">将 ASP.NET Web 服务代码迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="813dd-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="813dd-106">确保该服务存在一组综合测试。</span><span class="sxs-lookup"><span data-stu-id="813dd-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="813dd-107">为该服务生成 WSDL，并将一个副本保存在服务的 .asmx 文件所在的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="813dd-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="813dd-108">升级 ASP.NET Web 服务以使用 .NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="813dd-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="813dd-109">首先将.NET Framework 2.0 部署到在 IIS 中，应用程序，然后使用 Visual Studio 2005 来自动化代码转换过程中，如中所述[分步指南将 Web 项目从 Visual Studio.NET 2002年/2003 到 Visual Studio2005](http://go.microsoft.com/fwlink/?LinkId=96492)。</span><span class="sxs-lookup"><span data-stu-id="813dd-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="813dd-110">运行测试集。</span><span class="sxs-lookup"><span data-stu-id="813dd-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="813dd-111">为 `Namespace` 属性的 `Name` 和 <xref:System.Web.Services.WebService> 参数提供明确的值（如果尚未提供）。</span><span class="sxs-lookup"><span data-stu-id="813dd-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="813dd-112">为 `MessageName` 的 <xref:System.Web.Services.WebMethodAttribute> 参数执行同样的操作。</span><span class="sxs-lookup"><span data-stu-id="813dd-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="813dd-113">如果尚未为 SOAPAction HTTP 头（请求是通过此 HTTP 头路由到方法的）提供明确的值，则利用 `Action` 显式指定 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="813dd-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
5.  <span data-ttu-id="813dd-114">测试更改。</span><span class="sxs-lookup"><span data-stu-id="813dd-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="813dd-115">将类的方法体中任何独立存在的代码移到要使用原始类的单独的类中。</span><span class="sxs-lookup"><span data-stu-id="813dd-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
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
  
7.  <span data-ttu-id="813dd-116">测试更改。</span><span class="sxs-lookup"><span data-stu-id="813dd-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="813dd-117">将对 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 程序集 System.ServiceModel 和 System.Runtime.Serialization 的引用添加到 ASP.NET Web 服务项目。</span><span class="sxs-lookup"><span data-stu-id="813dd-117">Add references to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="813dd-118">运行[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]从 WSDL 的客户端类。</span><span class="sxs-lookup"><span data-stu-id="813dd-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class from the WSDL.</span></span> <span data-ttu-id="813dd-119">将生成的类模块添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="813dd-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="813dd-120">前面的步骤中生成的类模块包含接口定义。</span><span class="sxs-lookup"><span data-stu-id="813dd-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
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
  
     <span data-ttu-id="813dd-121">修改 ASP.NET Web 服务类的定义，这样该类可以定义为实现该接口，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="813dd-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
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
  
11. <span data-ttu-id="813dd-122">编译该项目。</span><span class="sxs-lookup"><span data-stu-id="813dd-122">Compile the project.</span></span> <span data-ttu-id="813dd-123">由于在步骤 9 中生成的代码与某些类型定义重复，所以可能存在一些错误。</span><span class="sxs-lookup"><span data-stu-id="813dd-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="813dd-124">一般通过删除这些预先存在的类型定义来修复这些错误。</span><span class="sxs-lookup"><span data-stu-id="813dd-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="813dd-125">测试更改。</span><span class="sxs-lookup"><span data-stu-id="813dd-125">Test the change.</span></span>  
  
12. <span data-ttu-id="813dd-126">移除 ASP.NET 特定的属性，如 <xref:System.Web.Services.WebService>、<xref:System.Web.Services.WebMethodAttribute> 和 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>。</span><span class="sxs-lookup"><span data-stu-id="813dd-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
13. <span data-ttu-id="813dd-127">配置类（现在为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务类型）以要求使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET 兼容模式，前提是 ASP.NET Web 服务依赖下列任意项：</span><span class="sxs-lookup"><span data-stu-id="813dd-127">Configure the class, which is now a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service type, to require [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="813dd-128"><xref:System.Web.HttpContext> 类。</span><span class="sxs-lookup"><span data-stu-id="813dd-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="813dd-129">ASP.NET 配置文件。</span><span class="sxs-lookup"><span data-stu-id="813dd-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="813dd-130">.asmx 文件上的 ACL。</span><span class="sxs-lookup"><span data-stu-id="813dd-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="813dd-131">IIS 身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="813dd-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="813dd-132">ASP.NET 模拟选项。</span><span class="sxs-lookup"><span data-stu-id="813dd-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="813dd-133">ASP.NET 全球化。</span><span class="sxs-lookup"><span data-stu-id="813dd-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="813dd-134">将原始 .asmx 文件重命名为 .asmx.old。</span><span class="sxs-lookup"><span data-stu-id="813dd-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="813dd-135">为服务创建一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务文件，为该文件指定扩展名 .asmx，然后将其保存到 IIS 中的应用程序根目录中。</span><span class="sxs-lookup"><span data-stu-id="813dd-135">Create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="813dd-136">将服务的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 配置添加到其 Web.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="813dd-136">Add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration for the service to its Web.config file.</span></span> <span data-ttu-id="813dd-137">配置服务以使用[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)，若要使用在前面的步骤中，创建扩展名为.asmx 服务文件和不为其自身，生成的 WSDL 但若要使用第 2 步中从 WSDL。</span><span class="sxs-lookup"><span data-stu-id="813dd-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="813dd-138">另外，还要将其配置为使用 ASP.NET 兼容模式（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="813dd-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
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
  
17. <span data-ttu-id="813dd-139">保存该配置。</span><span class="sxs-lookup"><span data-stu-id="813dd-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="813dd-140">编译该项目。</span><span class="sxs-lookup"><span data-stu-id="813dd-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="813dd-141">运行该测试集以确定所有更改均已生效。</span><span class="sxs-lookup"><span data-stu-id="813dd-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813dd-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="813dd-142">See Also</span></span>  
 [<span data-ttu-id="813dd-143">如何： 将 ASP.NET Web 服务客户端代码迁移到 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="813dd-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
