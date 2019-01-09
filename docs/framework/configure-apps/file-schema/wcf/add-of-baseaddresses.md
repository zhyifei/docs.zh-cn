---
title: '&lt;baseAddresses&gt; 的 &lt;add&gt; '
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: ce476c2d40758cf52eada813873d061d0e441bce
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149080"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a>&lt;baseAddresses&gt; 的 &lt;add&gt; 
表示一个配置元素，该元素指定服务主机所使用的基址。  
  
 \<system.ServiceModel>  
\<客户端 >  
\<终结点 >  
\<主机 >  
\<baseAddresses >  
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
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|一个 `baseAddress` 元素集合。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [承载](../../../../../docs/framework/wcf/feature-details/hosting.md)
