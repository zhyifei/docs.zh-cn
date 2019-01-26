---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730121"
---
# <a name="ltbaseaddressesgt"></a>&lt;baseAddresses&gt;
表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。 如果存在基址，则可以使用相对于基址的地址配置终结点。  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host>  
\<baseAddresses>  
  
## <a name="syntax"></a>语法  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|一个配置元素，指定服务主机所使用的基址。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<host>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|一个指定服务主机设置的配置元素。|  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [承载](../../../../../docs/framework/wcf/feature-details/hosting.md)
