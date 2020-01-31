---
title: 특성
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: c7bbbda88bd2fddb235b9ae639848e08a452c913
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741784"
---
# <a name="attributes"></a>특성
<xref:System.Attribute?displayProperty=nameWithType> 是用于定义自定义特性的基类。

 特性是可以添加到编程元素（例如程序集、类型、成员和参数）的注释。 它们存储在程序集的元数据中，可以在运行时使用反射 API 时访问。 例如，框架可以定义 <xref:System.ObsoleteAttribute>，它可以应用于某个类型或成员，指示该类型或成员已被弃用。

 特性可以具有一个或多个属性，这些属性包含与该特性相关的其他数据。 例如，`ObsoleteAttribute` 可以包含有关已过时的类型或成员的其他信息，以及替换过时 API 的新 API 的描述。

 应用特性时，必须指定该特性的某些属性。 这些被称为必需属性或必需参数，因为它们表示为位置型构造函数参数。 例如，<xref:System.Diagnostics.ConditionalAttribute> 的<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 属性是必需属性。

 应用该特性时不一定必须指定的属性称为可选属性（或可选参数）。 它们由可设置的属性表示。 编译器提供特殊语法，以在应用特性时设置这些属性。 例如， <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 属性表示了一个可选参数。

 ✔️命名具有后缀 "Attribute" 的自定义属性类。

 ✔️将 <xref:System.AttributeUsageAttribute> 应用于自定义属性。

 ✔️提供可选参数的可设置属性。

 ✔️确实提供必需参数的只需属性。

 ✔️提供构造函数参数来初始化对应于所需参数的属性。 每个参数应与相应的属具有相同的名称（尽管具有不同的大小写）。

 ❌ 避免提供构造函数参数来初始化对应于可选参数的属性。

 换句话说，不要使用可同时用构造函数和 setter 设置的属性。 此原则使哪些参数是可选的、哪些参数是必需的变得非常明确，并可避免使用两种方法执行相同的操作。

 ❌ 避免重载自定义特性构造函数。

 只使用一个构造函数来清晰地向用户传达哪些参数是必需的，哪些是可选的。

 如果可能，✔️确实密封自定义特性类。 这可使查找属性的速度更快。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
