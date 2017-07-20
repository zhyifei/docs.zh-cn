---
title: "用来控制 XML 序列化的特性 | Microsoft Docs"
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
  - "特性 [.NET Framework], XML 序列化"
  - "类, 序列化"
  - "序列化, 特性"
  - "XML 架构, 序列化"
  - "XML 序列化, 特性"
  - "XmlSerializer 类, 序列化"
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 用来控制 XML 序列化的特性
通过将下表中的特性应用于类和类成员，可以控制 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) 序列化或反序列化该类的实例的方式。若要了解这些特性如何控制 XML 序列化，请参见[使用特性控制 XML 序列化](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)。  
  
 这些特性还可用于控制 XML Web services 生成的文本样式的 SOAP 消息。有关将这些特性应用于 XML Web services 方法的更多信息，请参见 [使用 XML Web services 进行 XML 序列化](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)。  
  
 有关特性的更多信息，请参见[特性](../../../docs/standard/attributes/index.md)。  
  
|特性|适用对象|指定|  
|--------|----------|--------|  
|[XmlAnyAttributeAttribute](frlrfSystemXmlSerializationXmlAnyAttributeAttributeClassTopic)|公共字段、属性、参数或返回 [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic) 对象数组的返回值。|反序列化时，将会使用 [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic) 对象填充数组，而这些对象代表对于架构未知的所有 XML 特性。|  
|[XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic)|公共字段、属性、参数或返回 [XmlElement](frlrfSystemXmlXmlElementClassTopic) 对象数组的返回值。|反序列化时，将会使用 [XmlElement](frlrfSystemXmlXmlElementClassTopic) 对象填充数组，而这些对象代表对于架构未知的所有 XML 元素。|  
|[XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic)|公共字段、属性、参数或返回复杂对象数组的返回值。|数组成员将作为 XML 数组的成员生成。|  
|[XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic)|公共字段、属性、参数或返回复杂对象的数组的返回值。|可以插入数组的派生类型。通常与 [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic) 一起应用。|  
|[XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic)|公共字段、属性、参数或返回值。|成员将作为 XML 特性进行序列化。|  
|[XmlChoiceIdentifierAttribute](frlrfSystemXmlSerializationXmlChoiceIdentifierAttributeClassTopic)|公共字段、属性、参数或返回值。|可以使用枚举进一步消除成员的歧义。|  
|[XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic)|公共字段、属性、参数或返回值。|字段或属性将作为 XML 元素进行序列化。|  
|[XmlEnumAttribute](frlrfSystemXmlSerializationXmlEnumAttributeClassTopic)|作为枚举标识符的公共字段。|枚举成员的元素名称。|  
|[XmlIgnoreAttribute](frlrfSystemXmlSerializationXmlIgnoreAttributeClassTopic)|公共属性和公共字段。|序列化包含类时，应该忽略属性或字段。|  
|[XmlIncludeAttribute](frlrfSystemXmlSerializationXmlIncludeAttributeClassTopic)|公共派生类声明，以及 Web 服务描述语言 \(WSDL\) 文档的公共方法的返回值。|生成要在序列化时识别的架构时，应该将该类包括在内。|  
|[XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic)|公共类声明。|控制视为 XML 根元素的特性目标的 XML 序列化。使用该特性可进一步指定命名空间和元素名称。|  
|[XmlTextAttribute](frlrfSystemXmlSerializationXmlTextAttributeClassTopic)|公共属性和公共字段。|属性或字段应该作为 XML 文本进行序列化。|  
|[XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic)|公共类声明。|XML 类型的名称和命名空间。|  
  
 除了这些特性（全部位于 [System.Xml.Serialization](frlrfSystemxmlserialization) 命名空间中）之外，还可以将 [System.ComponentModel.DefaultValueAttribute](frlrfSystemComponentModelDefaultValueAttributeClassTopic) 特性应用于字段。**DefaultValueAttribute** 可以设置在未指定值时将自动分配给成员的值。  
  
 若要控制编码的 SOAP XML 序列化，请参见[用来控制编码的 SOAP 序列化的特性](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)。  
  
## 请参阅  
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [使用特性控制 XML 序列化](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [如何：指定 XML 流的替代元素名称](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [如何：序列化对象](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [如何：反序列化对象](../../../docs/framework/serialization/how-to-deserialize-an-object.md)