---
title: 简化配置
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 567f03e8f35ed72ba7e2a602bf47257158741fb3
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321155"
---
# <a name="simplified-configuration"></a>简化配置
配置 Windows Communication Foundation （WCF）服务可以是一种复杂的任务。 该任务涉及多个不同选项，并且有时会很难确定需要哪些设置。 虽然配置文件提高了 WCF 服务的灵活性，但是它们也是很难找到问题的源。 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]解决了这些问题，并向用户提供了一种减小服务配置大小和降低复杂性的方法。  
  
## <a name="simplified-configuration"></a>简化配置  
 在 WCF 服务配置文件中，< `system.serviceModel` > 部分包含每个托管服务的 < `service` > 元素。 < @No__t_0 > 元素包含 < `endpoint` 元素的集合，这些元素指定为每项服务公开的终结点以及一组服务行为（可选）。 < @No__t_0 > 元素指定终结点公开的地址、绑定和协定，以及绑定配置和终结点行为（可选）。 "< @No__t_0 >" 部分还包含 < `behaviors` 元素，可用于指定服务或终结点行为。 下面的示例演示配置文件的 < `system.serviceModel` > 部分。  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 通过 < `service` > 元素删除要求，使 WCF 服务配置更容易。 如果未 < `service` > 部分添加或在 < `service` > 部分中添加任何终结点，并且服务未以编程方式定义任何终结点，则会将一组默认终结点自动添加到服务中，每个服务基址对应一个终结点。和服务实现的每个协定。 在上述每个终结点中，终结点地址与基址相对应，绑定由基址方案确定，协定即为服务实现的协定。 如果你不需要指定任何终结点或服务行为，或者不需要更改任何绑定设置，则完全不必指定服务配置文件。 如果服务实现了两个协定，并且主机同时启用了 HTTP 和 TCP 传输，服务主机将创建四个默认终结点，使用每个传输的每一协定各对应一个终结点。 若要创建默认终结点，服务主机必须了解要使用的绑定。 这些设置在 "< `system.serviceModel` >" 部分的 < `protocolMappings` > "部分中指定。 "< @No__t_0 >" 部分包含映射到绑定类型的传输协议方案的列表。 服务主机使用传递到它的基址来确定要使用的绑定。 下面的示例使用 < `protocolMappings` > 元素。  
  
> [!WARNING]
> 更改默认配置元素（如绑定或行为）可能会影响在配置层次结构的较低级别中定义的服务，因为这些服务可能使用这些默认绑定和行为。 因而，更改默认绑定和行为的任何人员都需要注意，这些更改可能会影响层次结构中的其他服务。  
  
> [!NOTE]
> 承载于 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 下的服务使用虚拟目录作为其基址。  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 在上一示例中，基址以“http”方案开头的终结点使用 <xref:System.ServiceModel.BasicHttpBinding>。 基址以“net.tcp”方案开头的终结点使用 <xref:System.ServiceModel.NetTcpBinding>。 你可以在本地 App.config 或 Web.config 文件中重写相应设置。  
  
 "< @No__t_0 >" 部分中的每个元素必须指定方案和绑定。 还可以指定一个 `bindingConfiguration` 属性，该属性在配置文件的 < `bindings` > 部分中指定绑定配置。 如果未指定 `bindingConfiguration`，则使用相应绑定类型的匿名绑定配置。  
  
 使用匿名 < 为默认终结点配置服务行为 `behavior` < `serviceBehaviors` > 部分中 > 部分。 < @No__t_1 > 中的任何未命名 < `behavior` > 元素用于配置服务行为。 例如，下面的配置文件对主机中的所有服务启用服务元数据发布。  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 终结点行为是使用匿名 < `behavior` > < `serviceBehaviors` > 部分内的节来配置的。  
  
 下面示例中的配置文件使用简化配置模型，它等效于本主题开头的配置文件。  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> 此功能只与 WCF 服务配置相关，与客户端配置无关。 大多数时候，使用 svcutil.exe 之类的工具或从 Visual Studio 添加服务引用将生成 WCF 客户端配置。 如果要手动配置 WCF 客户端，则需要将 \<client > 元素添加到配置中，并指定希望调用的任何终结点。  
  
## <a name="see-also"></a>请参阅

- [使用配置文件配置服务](configuring-services-using-configuration-files.md)
- [配置服务绑定](configuring-bindings-for-wcf-services.md)
- [配置系统提供的绑定](./feature-details/configuring-system-provided-bindings.md)
- [配置服务](configuring-services.md)
- [配置 WCF 服务](configuring-services.md)
- [在代码中配置 WCF 服务](configuring-wcf-services-in-code.md)
