---
title: 简化配置
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 4e316290c045b75896c61e36c1646440c18678e2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249625"
---
# <a name="simplified-configuration"></a>简化配置
配置 Windows 通信基础 （WCF） 服务可能是一项复杂的任务。 该任务涉及多个不同选项，并且有时会很难确定需要哪些设置。 虽然配置文件提高了 WCF 服务的灵活性，但它们也是许多难以发现问题的根源。 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]解决了这些问题，并向用户提供了一种减小服务配置大小和降低复杂性的方法。  
  
## <a name="simplified-configuration"></a>简化配置  
 在 WCF 服务配置文件中，<>`system.serviceModel`部分包含托管的每个`service`服务<>元素。 <>`service`元素包含一个<>`endpoint`元素的集合，这些元素指定每个服务公开的终结点，并可以选择一组服务行为。 <>`endpoint`元素指定终结点公开的地址、绑定和协定，以及可选的绑定配置和终结点行为。 <>`system.serviceModel`部分还包含一个<>`behaviors`元素，允许您指定服务或终结点行为。 下面的示例显示了配置文件<>`system.serviceModel`部分。  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]通过删除<>`service`元素的要求，使配置 WCF 服务变得更加容易。 如果不在<>`service`节中添加`service`<>节或添加任何终结点，并且服务未以编程方式定义任何终结点，则会自动将一组默认终结点添加到服务中，每个服务基地址和服务实现的每个协定都添加一个终结点。 在上述每个终结点中，终结点地址与基址相对应，绑定由基址方案确定，协定即为服务实现的协定。 如果你不需要指定任何终结点或服务行为，或者不需要更改任何绑定设置，则完全不必指定服务配置文件。 如果服务实现了两个协定，并且主机同时启用了 HTTP 和 TCP 传输，服务主机将创建四个默认终结点，使用每个传输的每一协定各对应一个终结点。 若要创建默认终结点，服务主机必须了解要使用的绑定。 这些设置在<>`protocolMappings``system.serviceModel`节中的<>部分中指定。 <>`protocolMappings`部分包含映射到绑定类型的传输协议方案的列表。 服务主机使用传递到它的基址来确定要使用的绑定。 下面的示例使用<>`protocolMappings`元素。  
  
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
  
 <>`protocolMappings`部分中的每个元素必须指定方案和绑定。 或者，它可以指定一个`bindingConfiguration`属性，该属性在配置文件的<>`bindings`部分中指定绑定配置。 如果未指定 `bindingConfiguration`，则使用相应绑定类型的匿名绑定配置。  
  
 通过使用<>`behavior``serviceBehaviors`节中的匿名<>部分，为默认终结点配置服务行为。 <>`serviceBehaviors`中任何`behavior`未命名的<>元素都用于配置服务行为。 例如，下面的配置文件对主机中的所有服务启用服务元数据发布。  
  
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
  
 终结点行为通过使用<>`behavior``serviceBehaviors`节中的匿名<>部分进行配置。  
  
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
> 此功能只与 WCF 服务配置相关，与客户端配置无关。 大多数时候，使用 svcutil.exe 之类的工具或从 Visual Studio 添加服务引用将生成 WCF 客户端配置。 如果要手动配置 WCF 客户端，则需要向配置中添加\<客户端>元素，并指定要调用的任何终结点。  
  
## <a name="see-also"></a>请参阅

- [使用配置文件配置服务](configuring-services-using-configuration-files.md)
- [配置服务绑定](configuring-bindings-for-wcf-services.md)
- [配置系统提供的绑定](./feature-details/configuring-system-provided-bindings.md)
- [正在配置服务](configuring-services.md)
- [配置 WCF 服务](configuring-services.md)
- [在代码中配置 WCF 服务](configuring-wcf-services-in-code.md)
