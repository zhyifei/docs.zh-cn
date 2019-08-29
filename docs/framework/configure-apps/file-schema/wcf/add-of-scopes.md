---
title: <add> 的 <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926632"
---
# <a name="add-of-scopes"></a>\<添加作用域\<的 > >
添加可用于在查询时筛选服务终结点的自定义范围 URI。  
  
\<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
\<endpointDiscovery>  
\<scopes>  
\<add>  
  
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
  
|特性|描述|  
|---------------|-----------------|  
|范围|一个 URI，包含在匹配条件以查找服务时可使用的终结点的范围信息。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|包含一个配置元素集合，这些元素指定可用于在查询时筛选服务终结点的自定义范围 URI。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
