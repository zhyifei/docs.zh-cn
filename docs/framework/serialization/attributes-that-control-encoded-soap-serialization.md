---
title: "用来控制编码的 SOAP 序列化的特性 | Microsoft Docs"
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
  - "序列化, 特性"
  - "SOAP, XML 序列化"
  - "XML 序列化, 特性"
  - "XML 序列化, SOAP"
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 用来控制编码的 SOAP 序列化的特性
万维网联合会 \(www.w3.org\) 文档“简单对象访问协议 \(SOAP\) 1.1”\(Simple Object Access Protocol \(SOAP\) 1.1\) 包含可选章节（第 5 节），该节描述如何编码 SOAP 参数。要符合该规范的第 5 节，必须使用在 [System.Xml.Serialization](frlrfSystemXmlSerialization) 命名空间中找到的一组特殊特性。将这些特性适当应用于类和类的成员，然后使用 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) 序列化一个或多个类的实例。  
  
 下表显示特性、特性的应用范围及其作用。有关使用这些特性控制 XML 序列化的更多信息，请参见[如何：将对象序列化为 SOAP 编码的 XML 流](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)和[如何：重写编码的 SOAP XML 序列化](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)。  
  
 有关特性的更多信息，请参见[特性](../../../docs/standard/attributes/index.md)。  
  
|特性|适用对象|指定|  
|--------|----------|--------|  
|[SoapAttributeAttribute](frlrfSystemXmlSerializationSoapAttributeAttributeClassTopic)|公共字段、属性、参数或返回值。|类成员将序列化为 XML 特性。|  
|[SoapElementAttribute](frlrfSystemXmlSerializationSoapElementAttributeClassTopic)|公共字段、属性、参数或返回值。|类将序列化为 XML 元素。|  
|[SoapEnumAttribute](frlrfSystemXmlSerializationSoapEnumAttributeClassTopic)|作为枚举标识符的公共字段。|枚举成员的元素名称。|  
|[SoapIgnoreAttribute](frlrfSystemXmlSerializationSoapIgnoreAttributeClassTopic)|公共属性和公共字段。|序列化包含类时，应该忽略属性或字段。|  
|[SoapIncludeAttribute](frlrfSystemXmlSerializationSoapIncludeAttributeClassTopic)|公共的派生类声明，以及 Web 服务描述语言 \(WSDL\) 文档的公共方法。|生成要在序列化时识别的架构时，应该将该类型包括在内。|  
|[SoapTypeAttribute](frlrfSystemXmlSerializationSoapTypeAttributeClassTopic)|公共类声明。|类应序列化为 XML 类型。|  
  
## 请参阅  
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [如何：将对象序列化为 SOAP 编码的 XML 流](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)   
 [如何：重写编码的 SOAP XML 序列化](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)   
 [特性](../../../docs/standard/attributes/index.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [如何：序列化对象](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [如何：反序列化对象](../../../docs/framework/serialization/how-to-deserialize-an-object.md)