---
title: 추상화 구현을 위한 기본 클래스
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: b22923338f8488b6f7684e565f62d9afc16e6aa0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741782"
---
# <a name="base-classes-for-implementing-abstractions"></a>추상화 구현을 위한 기본 클래스
严格地说，当一个类派生出另一个类时，它就成了一个基类。 但是，在本部分中，基类是一个主要用于提供公共抽象的类，或者是供其他类通过继承重用某些默认实现的类。 基类通常位于继承层次结构的中间位置，位于根部的层次结构抽象和末端的一些自定义实现之间。

 它们可以为实现抽象提供帮助。 例如，框架中有序项集合的抽象之一是 <xref:System.Collections.Generic.IList%601> 接口。 实现 <xref:System.Collections.Generic.IList%601> 并不简单，因此框架提供了几个基类，例如 <xref:System.Collections.ObjectModel.Collection%601> 和 <xref:System.Collections.ObjectModel.KeyedCollection%602>，来为实现自定义集合提供帮助。

 基类通常不适合作为抽象本身，因为它们往往包含太多的实现。 例如，`Collection<T>` 基类包含许多实现，这些实现与一些实际情况有关，即它实现了非泛型的 `IList` 接口（目的是更好地与非泛型集合集成），并且它是存储在某个字段的内存中的项的集合。

 如前所述，基类可以为需要实现抽象的用户提供宝贵的帮助，但同时它们可能是一个重大的不利因素。 它们增加了继承层次结构的广度和深度，因此在概念上使框架更加复杂。 因此，只有在为框架用户提供巨大价值的时候才应使用基类。 如果它们仅对框架的实现者有用，则应该避免使用它们，在这种情况下，应该考虑委托到内部实现而不是从基类继承。

 ✔️考虑使基类抽象，即使它们不包含任何抽象成员也是如此。 这会清楚地告知用户该类根据设计只能用于继承。

 ✔️考虑将基类置于不同于主线方案类型的命名空间中。 根据定义，基类用于高级可扩展性场景，因此对大多数用户来说并没有意义。

 如果类用于公共 Api，则 ❌ 避免使用 "Base" 后缀命名基类。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
