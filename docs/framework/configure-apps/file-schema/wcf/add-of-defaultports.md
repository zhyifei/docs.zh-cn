---
title: '&lt;defaultPorts&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 0932ef9afacb6278c4857dcfd6ba545595ff8f9d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147715"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a>&lt;defaultPorts&gt; 的 &lt;add&gt;
客户端应用程序侦听的默认通信终结点。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<useRequestHeadersForMetadataAddress >  
\<d d >  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|端口|一个整数，指定默认通信端口号。|  
|scheme|一个字符串，指定与通信端口关联的协议设置组。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<d d >](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
