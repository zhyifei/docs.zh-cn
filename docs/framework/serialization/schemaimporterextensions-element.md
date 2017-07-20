---
title: "&lt;schemaImporterExtensions&gt; 元素 | Microsoft Docs"
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
  - "<schemaImporterExtensions> 元素"
  - "schemaImporterExtensions 元素"
  - "XML 序列化, 配置"
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;schemaImporterExtensions&gt; 元素
包含将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。  有关配置文件的更多信息，请参见 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。  
  
## 语法  
  
```  
  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## 子元素  
  
|元素|描述|  
|--------|--------|  
|[\<xmlSchemaImporterExtensions\> 的 \<add\> 元素](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)|添加创建映射时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。|  
  
## 父元素  
  
|元素|描述|  
|--------|--------|  
|[\<system.xml.serialization\> 元素](../../../docs/framework/serialization/system-xml-serialization-element.md)|用于控制 XML 序列化的顶级元素。|  
  
## 示例  
 下面的代码示例演示如何添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。  
  
```  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## 请参阅  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\> 元素](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<xmlSchemaImporterExtensions\> 的 \<add\> 元素](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\> 元素](../../../docs/framework/serialization/system-xml-serialization-element.md)