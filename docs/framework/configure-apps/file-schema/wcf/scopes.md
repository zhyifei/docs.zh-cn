---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: dd6513930798e9e1ab263f75c9350511c2dcdcd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935188"
---
# <a name="scopes"></a>\<scopes>
包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。  
  
\<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
\<endpointDiscovery>  
\<scopes>  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|特性|描述|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|添加可在匹配条件以查找服务时使用的终结点的范围信息。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
