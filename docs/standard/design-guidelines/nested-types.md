---
title: 嵌套类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c0eca851746899654636d36dce679acffc07ef0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="nested-types"></a>嵌套类型
嵌套的类型是在另一个类型，这称为封闭类型的范围内定义的类型。 嵌套的类型有权访问其封闭类型的所有成员。 例如，它有权访问在封闭类型和保护的封闭类型的所有祖先中定义的字段定义的私有字段。  
  
 一般情况下，应尽量少使用嵌套的类型。 其原因有若干： 一些开发人员不完全熟悉这一概念。 这些开发人员例如，可能会有问题的声明的嵌套类型的变量的语法。 嵌套的类型与其封闭类型，也非常紧密耦合，并且这种情况下为通用类型不适合。  
  
 嵌套的类型很适合于建模其封闭类型的实现详细信息。 最终用户应几乎不需要声明的嵌套类型的变量，并且几乎从未必须具有显式实例化嵌套的类型。 例如，集合的枚举器可以是该集合的嵌套的类型。 枚举器通常由其封闭类型实例化和枚举器变量许多语言都支持 foreach 语句，因为几乎无需最终用户声明。  
  
 **✓ 执行**使用嵌套的类型，从而使成员可访问性语义都需要的嵌套的类型和其外部类型之间的关系时。  
  
 **X 不**使用公共嵌套的类型作为自己的逻辑分组构造; 为此使用命名空间。  
  
 **请避免 x**公共公开嵌套的类型。 唯一的例外是如果需要仅在极少数情况下，例如生成子类或其他高级自定义应用场景中声明的嵌套类型的变量。  
  
 **X 不**使用嵌套的类型，如果类型为可能包含类型的外部引用。  
  
 例如，不应为类中的嵌套类型定义枚举传递给在类上定义的方法。  
  
 **X 不**使用嵌套的类型，如果他们需要通过客户端代码来实例化。  某个类型是否具有公共构造函数，它可能不应进行嵌套。  
  
 如果可实例化类型，这看起来以指示该类型具有其自身上的框架中的一个位置 （你可以创建、 使用它，以及销毁而完全不必使用外部类型），并因此不应进行嵌套。 在没有任何关系的外部类型之外，内部类型应不广泛重用承担到外部类型。  
  
 **X 不**定义为接口成员的嵌套的类型。 许多语言不支持这样的构造。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
