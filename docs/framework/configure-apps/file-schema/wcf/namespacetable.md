---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748875"
---
# <a name="ltnamespacetablegt"></a>&lt;namespaceTable&gt;

表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。

**\<system.serviceModel >**   
&nbsp;&nbsp;**\<路由 >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**

## <a name="syntax"></a>语法

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
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
| [**\<筛选器 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | 定义用于 XPath 表达式的命名空间前缀映射。 |

### <a name="parent-elements"></a>父元素

|     | 描述 |
| --- | ----------- |
| [**\<路由 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | 表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息，以及路由表定义到的目标终结点时使用将消息发送到筛选器匹配时。 |

## <a name="see-also"></a>请参阅

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
