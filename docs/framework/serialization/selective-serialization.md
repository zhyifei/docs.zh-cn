---
title: "有选择的序列化 | Microsoft Docs"
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
  - "二进制序列化, 有选择的序列化"
  - "序列化, 有选择的序列化"
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 有选择的序列化
类通常包含不应进行序列化的字段。例如，假定类将线程 ID 存储在成员变量中。如果反序列化该类，而在对该类进行序列化时，存储了该 ID 的线程可能不再运行。因此，序列化该值毫无意义。您可以防止对成员变量进行序列化，方法是使用 [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic) 特性标记它们，如下所述。  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```  
  
 如有可能，应使可能包含安全敏感数据的对象不可序列化。如果必须对该对象进行序列化，可将 **NonSerialized** 特性应用于存储敏感数据的特定字段。如果没有将这些字段排除在序列化之外，应该注意它们存储的数据将向有权序列化的所有代码公开。有关编写安全的序列化代码的更多信息，请参见[安全和序列化](../../../docs/framework/misc/security-and-serialization.md)。  
  
## 请参阅  
 [二进制序列化](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [安全和序列化](../../../docs/framework/misc/security-and-serialization.md)