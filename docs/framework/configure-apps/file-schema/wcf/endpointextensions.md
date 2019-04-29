---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 12ac8d9a7b0ed584fb1308e56d197a03b1c53e51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700873"
---
# <a name="endpointextensions"></a>\<endpointExtensions>
此节在计算机或应用程序配置文件的扩展节中注册新的标准终结点。 您可以向此集合添加标准终结点，具体方法为：使用 `add` 关键字，然后将元素的 `type` 特性设置为终结点类型，并将 `name` 特性设置为标准终结点的名称。  
  
 下面的示例使用 `add` 元素以及 `name` 特性将标准终结点添加到配置文件的 `<endpointExtensions>` 节。  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 在注册标准终结点之后，您可以按下例所示使用此终结点。 在中[\<终结点 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素，`kind`特性指定已在中注册的标准终结点类型`<endpointExtensions>`部分。 `endpointConfiguration`属性将与相同`name`属性中的标准终结点的配置元素的`<standardEndpoints>`部分。  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
