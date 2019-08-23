---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: fe57cb84cfa70b1f6b92abf1dbac89ddad9d4dc8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925702"
---
# <a name="endpointextensions"></a><span data-ttu-id="74acb-101">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="74acb-101">\<endpointExtensions></span></span>
<span data-ttu-id="74acb-102">此节在计算机或应用程序配置文件的扩展节中注册新的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="74acb-102">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="74acb-103">您可以向此集合添加标准终结点，具体方法为：使用 `add` 关键字，然后将元素的 `type` 特性设置为终结点类型，并将 `name` 特性设置为标准终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="74acb-103">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="74acb-104">下面的示例使用 `add` 元素以及 `name` 特性将标准终结点添加到配置文件的 `<endpointExtensions>` 节。</span><span class="sxs-lookup"><span data-stu-id="74acb-104">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="74acb-105">在注册标准终结点之后，您可以按下例所示使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="74acb-105">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="74acb-106">`kind` `<endpointExtensions>`在[终结点 > 元素中, 特性指定已在节中注册的标准终结点类型。 \<](endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="74acb-106">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="74acb-107">特性将与`<standardEndpoints>`节中的标准`name`终结点的配置元素的特性相同。 `endpointConfiguration`</span><span class="sxs-lookup"><span data-stu-id="74acb-107">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
