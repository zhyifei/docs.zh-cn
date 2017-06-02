---
title: "异常处理基础知识 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "公共语言运行时, 异常"
  - "异常, 示例"
  - "运行时, 异常"
ms.assetid: e865d48c-b862-4448-833e-09fcd48adf6b
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 异常处理基础知识
公共语言运行时支持基于异常对象和受保护代码块概念的异常处理模型。  运行时在异常发生时创建一个表示该异常的对象。  也可以通过从适当的基异常派生类来创建自己的异常类。  
  
 所有使用运行时的语言都以相似的方式处理异常。  每种语言都使用 Try\/Catch\/Finally 形式的结构化异常处理。  本节提供若干基本异常处理示例。  
  
## 本节内容  
 [如何：使用 Try\/Catch 块捕捉异常](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)  
 描述如何使用 Try\/Catch 块处理异常。  
  
 [如何：在 Catch 块中使用特定异常](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)  
 描述如何捕捉特定异常。  
  
 [如何：显式引发异常](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)  
 描述如何引发异常，并且描述如何在捕捉异常后再次引发这些异常。  
  
 [如何：创建用户定义的异常](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)  
 描述如何创建您自己的异常类。  
  
 [使用用户筛选的处理程序](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)  
 描述如何设置筛选异常。  
  
 [如何：使用 Finally 块](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)  
 解释如何在异常块中使用 Finally 语句。  
  
## 相关章节  
 [异常](../../../docs/standard/exceptions/index.md)  
 提供公共语言运行时异常的概述。  
  
 [异常类和属性](../../../docs/standard/exceptions/exception-class-and-properties.md)  
 描述异常对象的元素。