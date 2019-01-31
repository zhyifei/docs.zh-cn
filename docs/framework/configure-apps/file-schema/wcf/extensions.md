---
title: <extensions>
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: feac4999438a67043899eef98bb8b49644ee30d9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270012"
---
# <a name="extensions"></a><span data-ttu-id="1858e-101">\<扩展 ></span><span class="sxs-lookup"><span data-stu-id="1858e-101">\<extensions></span></span>
<span data-ttu-id="1858e-102">此配置元素包含一个 XML 元素集合，该集合包含随可检测到的标准元数据（EPR、ContractTypeName、BindingName、Scope 和 ListenURI）一起发布的自定义元数据。</span><span class="sxs-lookup"><span data-stu-id="1858e-102">This configuration element contains a collection of XML elements that contain custom metadata to be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span> <span data-ttu-id="1858e-103">下面是使用此配置元素的示例。</span><span class="sxs-lookup"><span data-stu-id="1858e-103">The following is an example of using this configuration element.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enable="true">
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="1858e-104">请参阅</span><span class="sxs-lookup"><span data-stu-id="1858e-104">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
