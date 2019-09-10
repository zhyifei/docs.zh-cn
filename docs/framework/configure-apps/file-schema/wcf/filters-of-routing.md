---
title: <filters> 的 <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855247"
---
# <a name="filters-of-routing"></a>\<筛选\<路由 > >

表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用<xref:System.ServiceModel.Dispatcher.MessageFilter>的 Windows Communication Foundation （WCF）的类型。

[ **\<system.serviceModel>** ](system-servicemodel.md)\
&nbsp;&nbsp;[ **\<routing>** ](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**  
  
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
| [ **\<filter>** ](filter.md) | 包含一个路由筛选器，该筛选器确定计算传入消息<xref:System.ServiceModel.Dispatcher.MessageFilter>时将使用的 Windows Communication Foundation （WCF）的类型。 |

### <a name="parent-elements"></a>父元素

|     | 描述 |
| --- | ----------- |
| [ **\<routing>** ](routing.md) | 表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时要<xref:System.ServiceModel.Dispatcher.MessageFilter>使用的 Windows Communication Foundation （WCF）的类型，以及用于定义目标终结点的路由表。当筛选器匹配时向发送消息。 |

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
