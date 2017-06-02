---
title: "动态源代码生成和编译 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "代码文档对象模型"
  - "CodeDOM"
  - "与语言无关的源代码建模"
  - "语言, CodeDOM 提供的多种语言支持"
  - "CodeDOM 支持的多种语言"
  - "多种语言的源代码"
  - "System.CodeDom 命名空间"
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 动态源代码生成和编译
.NET Framework 中包含一个名为“代码文档对象模型”\(CodeDOM\) 的机制，该机制使编写源代码的程序的开发人员可以在运行时，根据表示所呈现代码的单一模型，用多种编程语言生成源代码。  
  
 为表示源代码，CodeDOM 元素相互链接以形成一个数据结构（称为 CodeDOM 图），它以某种源代码的结构为模型。  
  
 `System.CodeDom` 命名空间定义可表示源代码逻辑结构（与具体的编程语言无关）的类型。  `System.CodeDom.Compiler` 命名空间定义从 CodeDOM 图生成源代码的类型，以及在受支持的语言中管理源代码编译的类型。  编译器供应商或开发人员可以扩展受支持语言的集合。  
  
 当程序需要用多种语言为程序模型或者为不确定的目标语言生成源代码时，与语言无关的源代码建模很有价值。  例如，如果语言的 CodeDOM 支持可用，则一些设计器将 CodeDOM 用作语言抽象接口，以用正确的编程语言生成源代码。  
  
 .NET Framework 中包含 [C\#](frlrfMicrosoftCSharpCSharpCodeProviderClassTopic)、[JScript](frlrfMicrosoftJScriptJScriptCodeProviderClassTopic) 和 [Visual Basic](frlrfMicrosoftVisualBasicVBCodeProviderClassTopic) 的代码生成器和代码编译器。  
  
## 本节内容  
 [使用 CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 介绍一般用途并演示如何使用 CodeDOM 生成简单的对象图。  
  
 [生成源代码和在 CodeDOM 图中编译程序](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 介绍如何使用 `System.CodeDom.Compiler` 命名空间中定义的类来生成源代码并使用外部编译器编译所生成的代码。  
  
 [如何：使用 CodeDOM 创建 XML 文档文件](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 描述了如何使用 CodeDOM 生成包含 XML 文档注释的代码，以及如何编译生成的代码，方可创建 XML 文档输出。  
  
 [如何：使用 CodeDOM 创建类](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 描述了如何使用 CodeDOM 生成包含字段、属性、方法、构造函数和入口点的类。  
  
## 参考  
 <xref:System.CodeDom>  
 定义在面向公共语言运行时的编程语言中表示代码元素的元素。  
  
 <xref:System.CodeDom.Compiler>  
 定义在运行时生成和编译代码的接口。  
  
## 相关章节  
 [CodeDOM Quick Reference](http://msdn.microsoft.com/zh-cn/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 为开发人员提供查找表示源代码元素的 CodeDOM 元素的快捷方法。