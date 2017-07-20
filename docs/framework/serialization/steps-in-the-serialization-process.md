---
title: "序列化过程中的步骤 | Microsoft Docs"
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
  - "二进制序列化, 步骤"
  - "序列化, 步骤"
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 序列化过程中的步骤
对[格式化程序](frlrfSystemRuntimeSerializationFormatterClassTopic)调用 [Serialize](frlrfSystemRuntimeSerializationFormatterClassSerializeTopic) 方法时，将按照以下规则顺序进行对象序列化：  
  
-   进行检查以确定格式化程序是否具有代理项选择器。如果有，则检查代理项选择器是否处理给定类型的对象。如果选择器处理该对象类型，则在代理项选择器上调用 **ISerializable.GetObjectData**。  
  
-   如果没有代理项选择器，或者代理项选择器不处理该对象类型，则进行检查以确定是否用 [Serializable](frlrfSystemSerializableAttributeClassTopic) 特性标记了该对象。如果未标记该对象，则会引发 [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic)。  
  
-   如果已相应地标记了对象，则检查该对象是否实现 [ISerializable](frlrfSystemRuntimeSerializationISerializableClassTopic) 接口。如果对象已实现该接口，则针对该对象调用 [GetObjectData](frlrfSystemRuntimeSerializationISerializableClassGetObjectDataTopic)。  
  
-   如果对象未实现 **ISerializable**，则使用默认序列化策略，从而序列化所有未标记为 [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic) 的字段。  
  
## 请参阅  
 [二进制序列化](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)