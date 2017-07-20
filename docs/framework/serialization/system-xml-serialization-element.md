---
title: "&lt;system.xml.serialization&gt; 元素 | Microsoft Docs"
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
  - "<system.xml.serialization> 元素"
  - "system.xml.serialization 元素"
  - "XML 序列化, 配置"
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;system.xml.serialization&gt; 元素
用于控制 XML 序列化的顶级元素。  有关配置文件的更多信息，请参见 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。  
  
## 语法  
  
```  
  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
 无。  
  
### 子元素  
  
|元素|描述|  
|--------|--------|  
|[\<dateTimeSerialization\> 元素](../../../docs/framework/serialization/datetimeserialization-element.md)|确定 <xref:System.DateTime> 对象的序列化模式。|  
|[\<schemaImporterExtensions\> 元素](../../../docs/framework/serialization/schemaimporterextensions-element.md)|包含将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。|  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|[\<configuration\> 元素](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|公共语言运行库和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
  
## 示例  
 下面的代码示例演示如何指定 <xref:System.DateTime> 对象的序列化模式，以及将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的其他类型。  
  
```  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## 请参阅  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\> 元素](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<schemaImporterExtensions\> 元素](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<xmlSchemaImporterExtensions\> 的 \<add\> 元素](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)