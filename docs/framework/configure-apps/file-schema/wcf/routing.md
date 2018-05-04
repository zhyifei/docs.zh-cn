---
title: '&lt;路由&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a>&lt;路由&gt;

表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息，以及路由表定义到的目标终结点时使用将消息发送到筛选器匹配时。

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;**\<路由 >**

## <a name="syntax"></a>语法

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

无

### <a name="child-elements"></a>子元素

|     | 描述 |
| --- | ----------- |
| [**\<筛选器 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | 包含一组路由筛选器确定计算传入消息时，将使用 Windows Communication Foundation (WCF) MessageFilter 的类型。 |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | 包含路由筛选器和目标终结点之间的映射，以便指定在筛选器匹配时使用的终结点。 |

### <a name="parent-elements"></a>父元素

|     | 描述 |
| --- | ----------- |
| **\<系统。ServiceModel >** | 所有 WCF 配置元素的根元素。 |

## <a name="see-also"></a>请参阅

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
