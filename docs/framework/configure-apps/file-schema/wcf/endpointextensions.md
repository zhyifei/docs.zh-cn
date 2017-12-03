---
title: '&lt;endpointExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b85ca7aaff3524eb34ad07d38913f8a846060f6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltendpointextensionsgt"></a>&lt;endpointExtensions&gt;
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
  
 在注册标准终结点之后，您可以按下例所示使用此终结点。 在[\<终结点 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素，`kind`特性指定已在中注册的标准终结点类型`<endpointExtensions>`部分。 `endpointConfiguration`特性将等于`name`中的标准终结点的配置元素的属性`<standardEndpoints>`部分。  
  
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
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```
