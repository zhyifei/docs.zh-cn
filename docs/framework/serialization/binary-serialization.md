---
title: "二进制序列化 | Microsoft Docs"
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
  - "二进制序列化"
  - "二进制序列化, 关于序列化"
  - "反序列化"
  - "序列化, 关于序列化"
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 二进制序列化
可以将序列化定义为一个将对象状态存储到存储介质的过程。在这个过程中，对象的公共字段和私有字段以及类（包括含有该类的程序集）的名称，将转换成字节流，而字节流接着将写入数据流。随后对该对象进行反序列化时，将创建原始对象的准确克隆。  
  
 在面向对象的环境中实现序列化机制时，必须多在易用性与灵活性之间做出权衡。很大程度上，这个过程可以自动完成，但前提是您对该过程拥有足够的控制权。例如，如果简单的二进制序列化不足，或者可能有特定原因决定需要对类中的哪些字段进行序列化，可能就会出现这种情况。以下章节说明了随 .NET Framework 一起提供的可靠序列化机制，并强调了根据需要自定义该过程所能使用的一些重要功能。  
  
> [!NOTE]
>  如果使用不同的 .NET Framework 版本序列化和反序列化以 UTF\-8 或 UTF\-7 编码的对象，则不保留该对象的状态。  
  
## 本节内容  
 [序列化概念](../../../docs/framework/serialization/serialization-concepts.md)  
 讨论序列化在其中有用的两种方案：在将数据保持到存储中以及在跨应用程序域传递对象时。  
  
 [基本序列化](../../../docs/framework/serialization/basic-serialization.md)  
 描述如何使用二进制格式化程序和 SOAP 格式化程序来序列化对象。  
  
 [有选择的序列化](../../../docs/framework/serialization/selective-serialization.md)  
 描述如何防止序列化某些类成员。  
  
 [自定义序列化](../../../docs/framework/serialization/custom-serialization.md)  
 描述如何使用 <xref:System.Runtime.Serialization.ISerializable> 接口自定义对类的序列化。  
  
 [序列化过程中的步骤](../../../docs/framework/serialization/steps-in-the-serialization-process.md)  
 描述对格式化程序调用 <xref:System.Runtime.Serialization.Formatter.Serialize%2A> 方法时序列化采取操作的过程。  
  
 [版本容错序列化](../../../docs/framework/serialization/version-tolerant-serialization.md)  
 介绍如何创建可序列化类型。在不导致应用程序引发异常的情况下，可以在以后对这样的类型进行修改。  
  
 [序列化准则](../../../docs/framework/serialization/serialization-guidelines.md)  
 提供一些通用准则，用于确定何时序列化对象。  
  
## 参考  
 <xref:System.Runtime.Serialization>  
 包含可用于序列化和反序列化对象的类。  
  
## 相关章节  
 [XML 和 SOAP 序列化](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 描述随公共语言运行时一起提供的 XML 序列化机制。  
  
 [安全和序列化](../../../docs/framework/misc/security-and-serialization.md)  
 描述写入执行序列化的代码时需要遵循的安全编码原则。  
  
 [Remote Objects](http://msdn.microsoft.com/zh-cn/515686e6-0a8d-42f7-8188-73abede57c58)  
 描述 .NET Framework 中为远程通信提供的多种通信方法。  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/zh-cn/1e64af78-d705-4384-b08d-591a45f4379c)  
 提供一些主题，描述并解释如何对使用 ASP.NET 创建的 XML Web services 进行编程。