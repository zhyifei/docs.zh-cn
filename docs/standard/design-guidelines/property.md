---
title: 属性设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
author: KrzysztofCwalina
ms.openlocfilehash: 1d119b48f0524b3e997aa2cb9ea2cbbd855afdf0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131451"
---
# <a name="property-design"></a>属性设计
虽然属性在技术上与方法非常相似，但它们的使用场景却截然不同。 属性应被视为聪明的字段。 它们兼具字段的调用语法和方法的灵活性。  
  
 **✓ DO** 创建仅限 get 的属性，如果调用方应不能更改属性的值。  
  
 请记住，如果类型的属性为可变引用类型，可以更改属性值，即使该属性是只读属性。  
  
 **X DO NOT** 仅属性的 setter 具有更广泛的可访问性比 getter 提供。  
  
 例如，请使用公共 setter 和受保护的 getter 使用属性。  
  
 如果不能提供的属性 getter，改为实现了与一种方法的功能。 请考虑从开始使用的方法名称`Set`并在后面加什么将已命名属性。 例如，<xref:System.AppDomain>有一个名为`SetCachePath`而不是让一个名为仅限组的属性`CachePath`。  
  
 **✓ DO** 提供的所有属性，确保，默认值不会导致安全漏洞或您对此低效代码的意义的默认值。  
  
 **✓ DO** 允许将属性按任何顺序设置，即使这会导致临时无效状态的对象。  
  
 提供对同一个对象的其他属性的值是常见的两个或多个要相互关联到一个属性的某些值可能无效的点的属性。 在这种情况下，从无效状态的异常应会推迟，直到实际对象一起使用相互关联的属性。  
  
 **✓ DO** 保留以前的值，如果属性 setter 将引发异常。  
  
 **X AVOID** 属性 getter 从引发异常。  
  
 属性 getter 应简单的操作，并且不应具有任何前置条件。 如果一个 getter 可能会引发异常，它应可能重新设计是一种方法。 请注意，此规则不适用于索引器，我们执行预期结果验证自变量异常的位置。  
  
### <a name="indexed-property-design"></a>索引的属性设计  
 索引的属性是一个特殊属性，可以有参数，可以在调用使用特殊语法类似于数组索引。  
  
 索引的属性通常被称为索引器。 应仅在提供的逻辑集合中的项的访问权限的 Api 中使用索引器。 例如，字符串是一系列字符，并使用索引器<xref:System.String?displayProperty=nameWithType>添加了以访问其中的字符。  
  
 **✓ 考虑**使用索引器提供对存储在内部数组中的数据的访问权限。  
  
 **✓ 考虑**为表示项目集合的类型提供索引器。  
  
 **X 避免**使用带有一个以上参数的索引属性。  
  
 如果设计需要多个参数，请重新考虑该属性是否真正代表逻辑集合的访问者。 如果不是，请改用方法。 考虑使用 `Get` 或 `Set` 开头的方法名称。  
  
 **X 避免** 使用具有 <xref:System.Int32?displayProperty=nameWithType>、<xref:System.Int64?displayProperty=nameWithType>、<xref:System.String?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType> 以外参数类型的索引器，或枚举。  
  
 如果设计需要其他类型的参数，强重新评估是否 API 确实表示对逻辑集合取值函数。 如果不是，使用一种方法。 考虑使用 `Get` 或 `Set` 开头的方法名称。  
  
 **✓ 务必**使用 `Item` 作为索引属性的名称，除非有明显更好的名称（例如，请参阅 `System.String` 上的 <xref:System.String.Chars%2A>属性）。  
  
 在 C# 中，索引器默认名称为 Item。 <xref:System.Runtime.CompilerServices.IndexerNameAttribute> 可用于自定义此名称。  
  
 **X 切忌**提供在语义方面等效的索引器和方法。  
  
 **X 切忌**在一种类型中提供多个重载索引器系列。  
  
 此准则由 C# 编译器强制执行。  
  
 **X 切忌**使用非默认索引属性。  
  
 此准则由 C# 编译器强制执行。  
  
### <a name="property-change-notification-events"></a>属性更改通知事件  
 有时，提供用于通知用户属性值更改的事件是很有用的。 例如，`System.Windows.Forms.Control` 在其 `Text` 属性的值发生变化后引发 `TextChanged` 事件。  
  
 **✓ CONSIDER** 引发更改通知事件修改高级 Api （通常是设计器组件） 中的属性值时。  
  
 如果用户可以知道当更改对象的属性的一个不错的方案，该对象会引发更改通知事件的属性。  
  
 但是，它不太可能值得对于之类的基类型或集合的低级 Api 引发此类事件的开销。 例如，<xref:System.Collections.Generic.List%601>不会引发此类事件时向列表添加新项和`Count`属性更改。  
  
 **✓ CONSIDER** 引发更改通知事件的属性的值更改通过外部强制时。  
  
 如果在属性值更改通过某种外部因素 （以通过在对象上调用方法以外的其他方式），则引发事件指示向开发人员的值正在更改和已更改。 一个典型示例是`Text`文本框控件的属性。 当用户键入文本中的`TextBox`，会自动更改的属性值。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
