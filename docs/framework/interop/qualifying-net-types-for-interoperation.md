---
title: "为互操作限定 .NET 类型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM 互操作, 公开 COM 组件"
  - "COM 互操作, 限定 .NET 类型"
  - "向 COM 公开 .NET Framework 组件"
  - "与非托管代码间的互操作, 公开 .NET Framework 组件"
  - "与非托管代码间的互操作, 限定 .NET 类型"
  - "为互操作限定 .NET 类型"
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 为互操作限定 .NET 类型
如果要向 COM 应用程序公开程序集中的类型，应考虑 COM 互操作在设计时的要求。  如果符合以下原则，托管类型（类、接口、结构和枚举）将与 COM 类型紧密集成：  
  
-   类应显式实现接口。  
  
     虽然 COM 互操作提供了一种机制来自动生成包含类的所有成员及其基类成员的接口，但最好提供显式接口。  自动生成的接口称作类接口。  有关指南，请参见[类接口简介](http://msdn.microsoft.com/zh-cn/733c0dd2-12e5-46e6-8de1-39d5b25df024)。  
  
     可以使用 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、C\# 和 C\+\+ 将接口定义合并在代码中，而不必使用接口定义语言 \(IDL\) 或其等效语言。  有关语法的详细信息，请参见您所用语言的文档。  
  
-   托管类型必须是公共的。  
  
     只有程序集中的公共类型才会注册并导出到类型库中。  因此，只有公共类型才对于 COM 可见。  
  
     托管类型将向其他未向 COM 公开的托管代码公开功能。  例如，参数化的构造函数、静态方法和常数字段不会向 COM 客户端公开。  此外，当运行时在类型中和类型外封送数据时，可能会复制或转换数据。  
  
-   方法、属性、字段和事件必须是公共的。  
  
     如果要对于 COM 可见，公共类型的成员也必须是公共的。  通过应用 <xref:System.Runtime.InteropServices.ComVisibleAttribute>，可以限制程序集、公共类型或公共类型的公共成员的可见性。  默认情况下，所有公共类型和成员都是可见的。  
  
-   类型必须有一个公共默认构造函数才能从 COM 中激活。  
  
     托管的公共类型对于 COM 是可见的。  但是，如果没有公共默认构造函数（无参数的构造函数），COM 客户端将无法创建该类型。  如果该类型由其他方法激活，则 COM 客户端仍可使用该类型。  
  
-   类型不能是抽象的。  
  
     COM 客户端和 .NET 客户端都不能创建抽象的类型。  
  
 当导出到 COM 后，托管类型的继承层次结构将被展平。  在托管和非托管环境之间，版本控制也会有所不同。  向 COM 公开的类型不具有与其他托管类型相同的版本控制特性。  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/zh-cn/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [应用互操作特性](../../../docs/framework/interop/applying-interop-attributes.md)   
 [将 COM 的程序集打包](../../../docs/framework/interop/packaging-an-assembly-for-com.md)