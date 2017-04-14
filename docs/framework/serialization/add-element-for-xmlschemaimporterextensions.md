---
title: "&lt;xmlSchemaImporterExtensions&gt; 的 &lt;add&gt; 元素 | Microsoft Docs"
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
  - "<xmlSchemaImporterExtensions> 的 <add> 元素"
  - "XML 序列化, 配置"
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;xmlSchemaImporterExtensions&gt; 的 &lt;add&gt; 元素
添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。  有关配置文件的更多信息，请参见 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。  
  
 \<XmlSchemaImporterExtensions\>  
\<add\>  
  
## 语法  
  
```  
  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|**name**|用于查找实例的简单名称。|  
|**type**|必需。  指定要添加的架构扩展类。  **type** 特性值必须位于一行上，并且包含完全限定的类型名。  当程序集放置在全局程序集缓存 \(GAC\) 中时，该特性值还必须包括已签名程序集的版本、区域性和公钥标记。|  
  
### 子元素  
 无。  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|\<xmlSchemaImporterExtensions\>|包含 <xref:System.Xml.Serialization.XmlSchemaImporter> 所使用的类型。|  
  
## 示例  
 下面的代码示例添加 XmlSchemaImporter 可以在映射类型时使用的扩展类型。  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## 请参阅  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 [\<system.xml.serialization\> 元素](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [\<schemaImporterExtensions\> 元素](../../../docs/framework/serialization/schemaimporterextensions-element.md)