---
title: <add> 的 <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926712"
---
# <a name="add-of-defaultports"></a>\<添加 defaultPorts > \<的 >
客户端应用程序侦听的默认通信终结点。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<useRequestHeadersForMetadataAddress>  
\<defaultPorts>  
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
|[\<defaultPorts>](defaultports.md)|一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
