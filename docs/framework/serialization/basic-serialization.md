---
title: "基本序列化 | Microsoft Docs"
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
  - "二进制序列化, 基本序列化"
  - "序列化, 基本序列化"
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 基本序列化
使类可序列化的最简单方法是按以下方式使用 [Serializable](frlrfSystemSerializableAttributeClassTopic) 特性对其进行标记。  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
 下面的代码示例演示如何将此类的实例序列化为文件。  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
 此示例使用二进制格式化程序执行序列化。您只需要创建流的实例以及要使用的格式化程序，然后在该格式化程序上调用 **Serialize** 方法。要序列化的流和对象将作为参数提供给此调用。尽管未在此示例中明确演示，但类的所有成员变量都将被序列化，即使将变量标记为私有也是如此。在这一方面，二进制序列化与 [XMLSerializer 类](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)不同，后者只序列化公共字段。有关从二进制序列化排除成员变量的信息，请参见[有选择的序列化](../../../docs/framework/serialization/selective-serialization.md)。  
  
 将对象还原回以前的状态同样很容易。首先，创建用于读取的流和[格式化程序](frlrfSystemRuntimeSerializationFormatterClassTopic)，然后指示该格式化程序反序列化对象。下面的代码示例演示如何完成以上过程。  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
 上面使用的 [BinaryFormatter](frlrfSystemRuntimeSerializationFormattersBinaryBinaryFormatterClassTopic) 非常有效，并可产生压缩字节流。使用此格式化程序序列化的所有对象也可使用它进行反序列化，这使得它成为对将在 .NET Framework 上反序列化的对象进行序列化的理想工具。需要特别注意的是，反序列化对象时不调用构造函数。这是出于性能原因而对反序列化进行的约束。然而，这违反了运行库对对象编写器制定的某些常用协定，并且将对象标记为可序列化时开发人员应确保了解其后果。  
  
 如果要求可移植，请改用 [SoapFormatter](frlrfSystemRuntimeSerializationFormattersSoapSoapFormatterClassTopic)。只需要将以上代码中的 **BinaryFormatter** 替换为 **SoapFormatter**，然后与前面一样调用 **Serialize** 和 **Deserialize**。此格式化程序针对以上使用的示例产生下面的输出：  
  
```  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:SOAP- ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP- ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle=  
  "http://schemas.microsoft.com/soap/encoding/clr/1.0"  
  "http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
 需要特别注意的是，无法继承 **Serializable** 特性。如果从 `MyObject` 派生新类，新类也必须标记为以上特性，否则将无法序列化。例如，尝试序列化以下类的实例时，将收到 [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic)，通知您 `MyStuff` 类型未标记为可序列化。  
  
```csharp  
public class MyStuff : MyObject   
{  
  public int n3;  
}  
```  
  
 使用 **Serializable** 特性非常方便，但有以上所述的限制。有关何时应标记类以进行序列化的信息，请参见[序列化准则](../../../docs/framework/serialization/serialization-guidelines.md)；在编译类后不能对类进行序列化。  
  
## 请参阅  
 [二进制序列化](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)