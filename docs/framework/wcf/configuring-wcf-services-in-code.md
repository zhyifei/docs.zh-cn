---
title: 在代码中配置 WCF 服务
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 714236bcdb562840323698622cdf3d0c6c89b6ca
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804142"
---
# <a name="configuring-wcf-services-in-code"></a>在代码中配置 WCF 服务
Windows Communication Foundation (WCF) 允许开发人员配置服务使用配置文件或代码。  当部署之后需要对服务进行配置时，配置文件十分有用。 在使用配置文件时，IT 专业人员只需要更新配置文件，无需重新编译。 不过，配置文件可能十分复杂，难以维护。 不支持对配置文件进行调试，并且将按名称来引用配置元素，这使得配置文件的创作易于出错且较为困难。 WCF 还允许你在代码中配置服务。 在早期版本的代码中的 WCF （4.0 及更早版本） 配置服务中十分方便，在自承载方案中，<xref:System.ServiceModel.ServiceHost>类允许你配置终结点和在调用 ServiceHost.Open 之前的行为。 但是，在 Web 承载方案中，您不具备针对 <xref:System.ServiceModel.ServiceHost> 类的直接访问权限。 若要配置 Web 承载的服务，您需要创建 `System.ServiceModel.ServiceHostFactory`，后者会创建 <xref:System.ServiceModel.Activation.ServiceHostFactory> 并执行任何所需的配置。 从.NET 4.5 开始，WCF 提供了更简单的方法来配置自承载和 web 承载服务的代码。  
  
## <a name="the-configure-method"></a>Configure 方法  
 只需在您的服务实现类中使用以下签名定义名为 `Configure` 的公共静态方法：  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Configure 方法采用 <xref:System.ServiceModel.ServiceConfiguration> 实例，使开发者可以添加终结点和行为。 打开服务主机之前，将 wcf 调用此方法。 定义后，将忽略 app.config 或 web.config 文件中指定的任何服务配置设置。  
  
 下面的代码段阐释如何定义 `Configure` 方法和添加服务终结点、终结点行为以及服务行为：  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 要为服务启用协议（如 https），可以显式添加使用协议的终结点，也可以通过调用 ServiceConfiguration.EnableProtocol(Binding) 自动添加终结点，这样可为与协议兼容的每个基址和定义的每个服务协定添加终结点。 下面的代码演示如何使用 ServiceConfiguration.EnableProtocol 方法：  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 中的设置 <`protocolMappings`> 如果没有任何应用程序终结点添加到仅使用部分<xref:System.ServiceModel.ServiceConfiguration>以编程方式。你可以从默认应用程序配置文件通过调用来根据需要加载服务配置<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>然后更改设置。 <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> 类还允许您从集中式配置加载配置。 下面的代码演示如何实现这一点：  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  请注意，<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>忽略 <`host`> 中的设置 <`service`> 标记 <`system.serviceModel`>。 从概念上讲，<`host`> 即将主机配置不服务配置，它获取加载之前执行此配置方法。  
  
## <a name="see-also"></a>请参阅  
 [使用配置文件配置服务](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [配置客户端行为](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [简化配置](../../../docs/framework/wcf/simplified-configuration.md)  
 [基于配置的激活](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [配置](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [IIS 和 WAS 中的基于配置的激活](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [配置和元数据支持](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [配置](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [如何：在配置中指定服务绑定](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [如何：在配置中创建服务终结点](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [如何：使用配置文件发布服务的元数据](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [如何：在配置中指定客户端绑定](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
