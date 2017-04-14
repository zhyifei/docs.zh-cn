---
title: "序列化概念 | Microsoft Docs"
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
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 序列化概念
为什么要使用序列化？两个最重要的原因是将对象状态保存到存储媒体，以便可以在以后阶段重新创建精确副本；以及将对象按值从一个应用程序域发送至另一个应用程序域。例如，序列化用于在 ASP.NET 中保存会话状态，并将对象复制到 Windows 窗体的剪贴板中。它还可用于在远程处理中将对象按值从一个应用程序域传递至另一个应用程序域。  
  
## 本节内容  
 [永久存储](../../../docs/framework/serialization/persistent-storage.md)  
 描述序列化对象的需要。  
  
 [按值封送](../../../docs/framework/serialization/marshal-by-value.md)  
 描述按值封送过程。  
  
## 相关章节  
 [二进制序列化](../../../docs/framework/serialization/binary-serialization.md)  
 描述随公共语言运行时一起提供的二进制序列化机制。  
  
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)  
 描述 .NET Framework 中为远程通信提供的多种通信方法。  
  
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 描述随公共语言运行时一起提供的 XML 和 SOAP 序列化机制。