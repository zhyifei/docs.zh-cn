---
title: "&lt;protocolMapping&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc534e3ccd3d965b76354bcc054b789af5fc4efd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;protocolMapping&gt; 的 &lt;add&gt;
表示传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 之间的默认协议映射和[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]绑定。 当在运行时创建默认终结点时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 将查看已配置的映射，并确定要用于基于特定内容的地址的绑定。  
  
 \<system.serviceModel >  
\<protocolMapping >  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|元素|描述|  
|-------------|-----------------|  
|绑定|一个字符串，指定在创建默认终结点时要用于终结点的绑定类型。|  
|bindingConfiguration|一个字符串，指定要引用的绑定配置节的名称。|  
|scheme|要用于默认终结点的传输协议方案。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|表示一个配置节，用于定义传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 之间的默认协议映射和[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]绑定。|  
  
## <a name="example"></a>示例  
 下面的配置示例演示 machine.config 文件中的默认协议映射。 您可以通过修改 machine.config 文件在计算机级别重写此默认映射。 或者，如果您只希望在应用程序范围内重写此映射，则可以在应用程序配置文件中重写此节，并为单独的协议方案更改映射。  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
