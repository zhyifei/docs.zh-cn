---
title: '&lt;namespaceTable&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: ef4f1c46a0ee3b94e5548b752e4e0a6a759fd45b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149509"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a>&lt;namespaceTable&gt; 的 &lt;add&gt;
表示一个配置元素，此元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。  
  
 \<system.serviceModel>  
\<路由 >  
\<namespaceTable >  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|namespace|一个包含命名空间的字符串。|  
|prefix|一个包含此命名空间的前缀的字符串。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<namespaceTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
