---
title: '&lt;schemaImporterExtensions&gt; 元素'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 8bcd8abb138c645f61bf833b49cda2631d1778dd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513108"
---
# <a name="ltschemaimporterextensionsgt-element"></a>&lt;schemaImporterExtensions&gt; 元素
包含将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。 有关配置文件的详细信息，请参阅[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。  
  
## <a name="syntax"></a>语法  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<添加 > 元素\<schemaImporterExtensions >](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|添加 <xref:System.Xml.Serialization.XmlSchemaImporter> 用来创建映射的类型。|  
  
## <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.xml.serialization> 元素](../../../docs/standard/serialization/system-xml-serialization-element.md)|用于控制 XML 序列化的顶级元素。|  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<dateTimeSerialization> 元素](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [\<添加 > 元素\<schemaImporterExtensions >](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
 [\<system.xml.serialization> 元素](../../../docs/standard/serialization/system-xml-serialization-element.md)
