---
title: "&lt;xmlSerializer&gt; 元素 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<xmlSerializer> 元素"
  - "XML 序列化, 配置"
  - "xmlSerializer 元素"
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;xmlSerializer&gt; 元素
指定是否完成 <xref:System.Xml.Serialization.XmlSerializer> 进度的额外检查。  
  
## 语法  
  
```  
  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|**checkDeserializeAdvances**|指定是否已检查 <xref:System.Xml.Serialization.XmlSerializer> 的进度。  将特性设置为“true”或“false”。  默认值为“true”。|  
|**useLegacySerializationGeneration**|指定 <xref:System.Xml.Serialization.XmlSerializer> 是否使用旧的序列化生成，该方法通过将 C\# 代码写入到一个文件，然后将其编译为程序集来生成程序集。  默认值为 **false**。|  
  
### 子元素  
 无。  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|[\<system.xml.serialization\> 元素](../../../docs/framework/serialization/system-xml-serialization-element.md)|包含 <xref:System.Xml.Serialization.XmlSerializer> 和 <xref:System.Xml.Serialization.XmlSchemaImporter> 类的配置设置。|  
  
## 备注  
 默认情况下，当反序列化不受信任的数据时，<xref:System.Xml.Serialization.XmlSerializer> 会额外提供一层防范潜在拒绝服务攻击的安全保护。  它通过在反序列化期间尝试检测无限循环来实现以上保护。  如果检测到以上状况，则引发异常并显示以下消息：“内部错误: 反序列化无法越过基础流。”  
  
 接收到此消息并不一定表示正在发生拒绝服务攻击。  在某些极少出现的情况下，无限循环检测机制会产生误报，并对合法的传入消息引发异常。  如果发现在您的特定应用程序中，合法消息被这一额外的保护层拒绝，则将 **checkDeserializeAdvances** 属性设置为“false”。  
  
## 示例  
 下面的代码示例将 **checkDeserializeAdvances** 属性设置为“false”。  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## 请参阅  
 <xref:System.Xml.Serialization.XmlSerializer>   
 [\<system.xml.serialization\> 元素](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)