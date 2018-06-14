---
title: '&lt;routing&gt; 的 &lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753110"
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;routing&gt; 的 &lt;filters&gt;

表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息时使用。

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;[**\<路由 >**](routing.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<筛选器 >**

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
| [**\<筛选器 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | 包含路由筛选器用于确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息时将使用。 |

### <a name="parent-elements"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<路由 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | 表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息，以及路由表定义到的目标终结点时使用将消息发送到筛选器匹配时。 |

## <a name="see-also"></a>请参阅

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
