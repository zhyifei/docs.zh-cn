---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936276"
---
# <a name="servicediscovery"></a>\<serviceDiscovery>
指定服务终结点的可发现性。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<serviceDiscovery>  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|一个公告终结点集合。 使用此节可指定用于发送公告消息的终结点。|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|一个发现终结点集合。 使用此节可指定要在其上侦听发现消息的终结点。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|指定行为元素。|  
  
## <a name="remarks"></a>备注  
 将此配置元素添加到服务的行为配置后，此元素可使系统检测到此服务的所有终结点。 可以通过使用[ \<discoveryEndpoint >](discoveryendpoint.md)或[ \<announcementEndpoint >](announcementendpoint.md)子元素, 进一步配置此类终结点的发现功能。 使用 " [ \<announcementEndpoint >](announcementendpoint.md) " 部分, 通过指定要用于发送服务公告的终结点配置 (online/Hello 和 offline/再见) 来配置公告。 使用 " [ \<discoveryEndpoint >](discoveryendpoint.md) " 部分, 手动指定要在其上侦听发现消息的终结点。  
  
## <a name="example"></a>示例  
 下面的配置示例指定 CalculatorService 可供检测，并选择指定要使用的公告终结点。  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
