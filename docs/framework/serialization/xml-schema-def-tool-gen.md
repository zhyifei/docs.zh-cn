---
title: "如何：使用 XML 架构定义工具生成类和 XML 架构文档 | Microsoft Docs"
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
  - "使用 XML 架构定义工具生成 XML 类"
  - "使用 XML 架构定义工具生成 XML 架构文档"
  - "XML 架构定义工具, 用于生成符合特定架构的类"
  - "XML 架构定义工具, 用于生成 XML 架构文档"
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 如何：使用 XML 架构定义工具生成类和 XML 架构文档
使用 XML 架构定义工具 \(Xsd.exe\) 可以生成描述类的 XML 架构，也可以生成 XML 架构定义的类。下面的过程说明如何执行这两种操作。  
  
### 生成符合特定架构的类  
  
1.  打开命令提示。  
  
2.  将 XML 架构作为参数传递给 XML 架构定义工具，该工具将创建与 XML 架构精确匹配的一组类，例如：  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     该工具只能处理引用万维网联合会 2001 年 3 月 16 日的 XML 规范的架构。换句话说，XML 架构命名空间必须是“http:\/\/www.w3.org\/2001\/XMLSchema”，如下面的示例所示。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3.  必要时用方法、属性或字段修改类。有关用特性修改类的更多信息，请参见[使用特性控制 XML 序列化](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)和[用来控制编码的 SOAP 序列化的特性](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)。  
  
 当序列化一个或多个类的实例后，检查生成的 XML 流的架构通常非常有用。例如，您可能发布架构以供其他人使用，或者可能将其与想达成一致的架构进行比较。  
  
#### 从一组类生成 XML 架构文档  
  
1.  将一个或多个类编译成 DLL。  
  
2.  打开命令提示。  
  
3.  将 DLL 作为参数传递给 Xsd.exe，例如：  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     架构将被写入，且以名称“schema0.xsd”开头。  
  
## 请参阅  
 [XML 架构定义工具和 XML 序列化](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [XML 序列化简介](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [DataSet](frlrfSystemDataDataSetClassTopic)   
 [XML 架构定义工具 \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [如何：序列化对象](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [如何：反序列化对象](../../../docs/framework/serialization/how-to-deserialize-an-object.md)