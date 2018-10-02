---
title: 用于实现抽象的基类
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f326ee895251678c7a23ea84a11e83951edf2cc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677066"
---
# <a name="base-classes-for-implementing-abstractions"></a>用于实现抽象的基类
严格地说，一个类成为基类时另一个类派生。 但是，对于本部分中，基类是主要用于提供常见抽象或重复使用某些其他类的默认实现但继承的类。 基类，这些类通常位于继承层次结构，层次结构的根处的抽象和底部的多个自定义实现之间的中间。  
  
 它们用于实现抽象处理为实现帮助器。 例如，一项的有序集合的框架的抽象是<xref:System.Collections.Generic.IList%601>接口。 实现<xref:System.Collections.Generic.IList%601>并非易事，并因此框架提供多个基类，例如<xref:System.Collections.ObjectModel.Collection%601>和<xref:System.Collections.ObjectModel.KeyedCollection%602>，它用于实现自定义集合作为帮助程序。  
  
 基本类并通常不适合作为抽象本身，因为他们往往会包含太多实现。 例如，`Collection<T>`基类提供了很多实现这一事实，它实现非泛型相关的`IList`接口 （若要将与非泛型集合更好地集成），它是一系列项存储在中的一个字段的内存。  
  
 如前面所述，基类，这些类可以提供宝贵帮助的用户需要实现的抽象，但在同一时间可重大的责任。 他们添加外围和增加的继承层次结构的深度和使框架，因此在概念上变得复杂。 因此，仅当它们带来巨大价值的框架用户，则应使用基类，这些类。 如果它们仅对 framework，在其中写委派而不是继承的内部实现从基类则强烈建议的实施者提供的值，它们应避免使用。  
  
 **✓ CONSIDER** 进行基本类抽象，即使它们不包含任何抽象成员。 这清楚地传达给用户的类仅用于从继承。  
  
 **✓ CONSIDER** 置于单独的命名空间从主线方案类型的基类，这些类。 根据定义，基类，这些类适用于高级的扩展性方案，因此都不会用到的大部分用户。  
  
 **X AVOID** 命名为"基本"后缀的基类，如果类旨在用于在公共 Api 中使用。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
