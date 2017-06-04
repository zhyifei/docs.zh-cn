---
title: "&lt;dateTimeSerialization&gt; 元素 | Microsoft Docs"
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
  - "<dateTimeSerialization> 元素"
  - "dateTimeSerialization 元素"
  - "XML 序列化, 配置"
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;dateTimeSerialization&gt; 元素
确定 <xref:System.DateTime> 对象的序列化模式。  
  
## 语法  
  
```  
  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|`mode`|可选。  指定序列化模式。  设置为 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 值之一。  默认值为 **RoundTrip**。|  
  
### 子元素  
 无。  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|system.xml.serialization|用于控制 XML 序列化的顶级元素。|  
  
## 备注  
 在 .NET Framework 1.0、1.1、2.0 以及更高版本中，当将此属性设置为 **Local** 时，<xref:System.DateTime> 对象总是格式化为本地时间。  即，序列化的数据中总是包含本地时区信息。  将此属性设置为 **Local** 可确保与较早版本的 .NET Framework 相兼容。  
  
 在 .NET Framework 2.0 及更高版本中，将此属性设置为 **Roundtrip** 时，系统会检查 <xref:System.DateTime> 对象以确定这些对象是否位于本地时区、UTC 时区或未指定的时区中。  随后会序列化 <xref:System.DateTime> 对象并保留该信息。  这是默认行为，建议为所有不与 Framework 的较早版本通信的新应用程序使用此行为。  
  
## 请参阅  
 <xref:System.DateTime>   
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<schemaImporterExtensions\> 元素](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<xmlSchemaImporterExtensions\> 的 \<add\> 元素](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\> 元素](../../../docs/framework/serialization/system-xml-serialization-element.md)