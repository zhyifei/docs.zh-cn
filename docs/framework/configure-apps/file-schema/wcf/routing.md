---
title: "&lt;路由&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cbe682ef9f7bca25ab4f5089a295ada9a00a8bc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltroutinggt"></a>&lt;路由&gt;

表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及用于定义在筛选器匹配时消息发送到的目标终结点的路由表。

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
| [**\<筛选器 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | 包含一组路由筛选器，这些筛选器确定计算传入消息时将使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter 的类型。 |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | 包含路由筛选器和目标终结点之间的映射，以便指定在筛选器匹配时使用的终结点。 |

### <a name="parent-elements"></a>父元素

|     | 描述 |
| --- | ----------- |
| **\<系统。ServiceModel >** | 所有 WCF 配置元素的根元素。 |

## <a name="see-also"></a>请参阅

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
