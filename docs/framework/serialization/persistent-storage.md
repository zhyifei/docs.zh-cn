---
title: "永久存储 | Microsoft Docs"
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
  - "二进制序列化, 永久存储"
  - "永久存储"
  - "序列化, 永久存储"
ms.assetid: b112c0dd-93e2-4eef-908d-5963f80bab65
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 永久存储
经常有必要将对象的字段值存储至磁盘，以后再检索此数据。尽管不依赖序列化也能很容易地实现这一点，但方法通常麻烦而容易出错，并且需要跟踪对象的层次结构时会逐渐变得更加复杂。假设要编写一个包含数千个对象的大型商务应用程序，并且必须为每个对象编写代码，以便将字段和属性保存至磁盘以及从磁盘进行还原。序列化为实现这一目标提供了方便的机制。  
  
 公共语言运行库可管理对象在内存中存储的方式，并通过使用[反射](../../../docs/framework/reflection-and-codedom/reflection.md)提供一种自动序列化机制。当序列化对象时，类的名称、程序集和类实例的所有数据成员被写入存储区。对象经常以成员变量方式将引用存储至其他实例。当序列化类时，序列化引擎跟踪被引用的对象（已序列化），以确保同一对象不会被多次序列化。随 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 一起提供的序列化体系结构可自动正确地处理对象图和循环引用。对于对象图的唯一要求是，也必须将已序列化的对象引用的所有对象标记为 [Serializable](frlrfSystemSerializableAttributeClassTopic)（有关更多信息，请参见[基本序列化](../../../docs/framework/serialization/basic-serialization.md)）。如果未进行标记，序列化程序尝试序列化未标记的对象时将引发异常。  
  
 当反序列化已序列化的类时，将重新创建该类，并且将自动还原所有数据成员的值。  
  
## 请参阅  
 [序列化概念](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)