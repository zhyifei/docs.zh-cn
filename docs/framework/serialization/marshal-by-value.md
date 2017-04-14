---
title: "按值封送 | Microsoft Docs"
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
  - "二进制序列化, 按值封送"
  - "按值封送对象"
  - "序列化, 按值封送"
ms.assetid: ee91e8f0-92e0-4732-8015-d17dee154be1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 按值封送
对象仅在创建它们的应用程序域中有效。除非对象从 [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) 派生或者标记为 [Serializable](frlrfSystemSerializableAttributeClassTopic)，否则尝试将对象作为参数传递或者作为结果返回时都将失败。如果将对象标记为 **Serializable**，则会自动序列化该对象，将该对象从一个应用程序域传输至另一个应用程序域，然后反序列化，以便在第二个应用程序域中生成该对象的一个精确副本。此过程通常称为按值封送。  
  
 如果对象从 **MarshalByRefObject** 派生，则会将对象引用（而不是对象本身）从一个应用程序域传递至另一个应用程序域。您还可以将从 **MarshalByRefObject** 派生的对象标记为 **Serializable**。此对象用于远程处理时，已使用代理项选择器 \([SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)\) 预配置负责序列化的格式化程序，该格式化程序控制序列化过程，并用代理替换从 [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) 派生的所有对象。如果本地没有 [SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)，则序列化体系结构遵循[序列化过程中的步骤](../../../docs/framework/serialization/steps-in-the-serialization-process.md)中所述的标准序列化规则。  
  
## 请参阅  
 [序列化概念](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)