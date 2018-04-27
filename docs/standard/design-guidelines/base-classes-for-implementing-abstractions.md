---
title: 用于实现抽象的基类
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 70d107d96576b8cafe9e76135c00bd2c635f2d7e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="base-classes-for-implementing-abstractions"></a>用于实现抽象的基类
严格地说，一个类成为基类，当另一个类派生自它时。 但是，对于本部分中，基类是主要用于提供公共抽象或重复使用某些其他类的默认实现但继承的类。 继承层次结构，在层次结构的根的抽象和一些自定义实现底部之间的中间通常位于基类，这些类。  
  
 它们作为实现帮助器用于实现抽象。 例如，其中一个有序集合的项的框架的抽象是<xref:System.Collections.Generic.IList%601>接口。 实现<xref:System.Collections.Generic.IList%601>非同小可，并因此框架提供多个基类，例如<xref:System.Collections.ObjectModel.Collection%601>和<xref:System.Collections.ObjectModel.KeyedCollection%602>，其用于实现自定义集合用作帮助器。  
  
 基类，这些类通常是不适合用作抽象本身，因为它们往往包含过多的实现。 例如，`Collection<T>`基类包含大量与它实现非泛型的事实相关的实现`IList`接口 （以与非泛型集合更好地集成），并在事实项的集合存储在内存中其域中的一个。  
  
 如前面所述，基类，这些类可以提供有用的帮助的用户需要实现抽象，但同时也可以是重大的责任。 他们添加外围应用和增加继承层次结构的深度并因此从概念上讲在框架上变得复杂化。 因此，仅当它们对框架的用户提供巨大价值，则应使用基类，这些类。 如果它们仅对的框架，在其中的内部实现，而不是继承自基类的区分大小委派应强考虑实施者提供值，它们应避免使用。  
  
 **请考虑 ✓**进行基本类抽象，即使它们不包含任何抽象成员。 它清楚地与用户建立通信，类旨在只是为了从继承。  
  
 **请考虑 ✓**置于单独的命名空间从主线方案类型的基类，这些类。 根据定义，基类，这些类旨在供高级的扩展性方案，因此不感兴趣的大多数用户。  
  
 **请避免 x**命名为"基本"后缀的基类，如果类旨在用于在公共 Api 中使用。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
