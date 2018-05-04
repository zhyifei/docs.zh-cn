---
title: '&lt;baseAddresses&gt; 的 &lt;add&gt; '
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: 3f1b7e8f1f4ab8542270d459ce5020ce4320eea9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a>&lt;baseAddresses&gt; 的 &lt;add&gt; 
表示一个配置元素，该元素指定服务主机所使用的基址。  
  
 \<system.ServiceModel>  
\<客户端 >  
\<终结点 >  
\<主机 >  
\<基址 >  
\<baseAddress >  
  
## <a name="syntax"></a>语法  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`baseAddress`|一个字符串，指定服务主机所使用的基址。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<基址 >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|一个 `baseAddress` 元素集合。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [承载](../../../../../docs/framework/wcf/feature-details/hosting.md)
