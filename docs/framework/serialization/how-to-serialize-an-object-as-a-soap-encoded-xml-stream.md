---
title: "如何：将对象序列化为 SOAP 编码的 XML 流 | Microsoft Docs"
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
  - "序列化, SOAP"
  - "SOAP, XML 序列化"
  - "XML 序列化, SOAP"
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 如何：将对象序列化为 SOAP 编码的 XML 流
[代码示例](#cpconxmlserializationusingsoapprotocolanchor1)  
  
 由于 SOAP 消息是使用 XML 生成的，因此 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) 可用于序列化类和生成编码的 SOAP 消息。结果 XML 符合万维网联合会 \(www.w3.org\) 文档“简单对象访问协议 \(SOAP\) 1.1”的第 5 节。如果您要创建通过 SOAP 消息进行通信的 XML Web services，则可以将一组特殊的 SOAP 特性应用于类和类的成员来自定义 XML 流。有关特性的列表，请参见[用来控制编码的 SOAP 序列化的特性](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)。  
  
### 将对象序列化为 SOAP 编码的 XML 流  
  
1.  使用 [XML 架构定义工具 \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md) 创建类。  
  
2.  应用在 **System.Xml.Serialization** 中找到的一个或多个特殊特性。请参见“用来控制编码的 SOAP 序列化的特性”中的列表。  
  
3.  通过创建新的 **SoapReflectionImporter**，然后用已序列化类的类型调用 **ImportTypeMapping** 方法，来创建 **XmlTypeMapping**。  
  
     下面的代码示例调用 **SoapReflectionImporter** 类的 **ImportTypeMapping**方法，来创建 **XmlTypeMapping**。  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
    ImportTypeMapping(GetType(Group))  
  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().  
    ImportTypeMapping(typeof(Group));  
    ```  
  
4.  通过将 **XmlTypeMapping** 传递给 <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> 构造函数，来创建 **XmlSerializer** 类的实例。  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  调用 **Serialize** 或 **Deserialize** 方法。  
  
## 示例  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
ImportTypeMapping(GetType(Group))  
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().ImportTypeMapping(typeof(Group));  
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## 请参阅  
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [用来控制编码的 SOAP 序列化的特性](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [使用 XML Web services 进行 XML 序列化](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)   
 [如何：序列化对象](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [如何：反序列化对象](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [如何：重写编码的 SOAP XML 序列化](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)