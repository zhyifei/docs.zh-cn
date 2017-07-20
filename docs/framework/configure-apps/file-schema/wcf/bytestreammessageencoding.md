---
title: "&lt;byteStreamMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;byteStreamMessageEncoding&gt;
指定消息编码作为字节流，也可以选择指定字符编码。  
  
## 语法  
  
```  
  
<byteStreamMessageEncoding/>  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|messageVersion|指定使用此绑定发送的消息的 SOAP 版本。  此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。  字节流消息编码器不支持其他任何消息版本。<br /><br /> 此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。|  
  
### 子元素  
  
|元素|描述|  
|--------|--------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。  此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。|  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|[\<绑定\>](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## 请参阅  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>   
 [消息编码](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [选择消息编码器](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [绑定](../../../../../docs/framework/wcf/bindings.md)   
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)