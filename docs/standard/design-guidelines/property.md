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
尽管从技术上讲非常类似于方法属性，但它们是在其使用情况方面大不相同。 它们应视为智能字段。 它们具有的字段中，调用语法和方法的灵活性。  
  
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
  
 **✓ CONSIDER** 使用索引器以提供对存储在内部数组中的数据访问。  
  
 **✓ CONSIDER** 提供索引器上表示的项的集合的类型。  
  
 **X AVOID** 使用索引与多个参数的属性。  
  
 如果设计需要多个参数，请重新考虑是否将属性确实表示对逻辑集合取值函数。 如果未显示，而是使用方法。 请考虑从开始使用的方法名称`Get`或`Set`。  
  
 **X AVOID** 具有以外的其他参数类型的索引器<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Int64?displayProperty=nameWithType>， <xref:System.String?displayProperty=nameWithType>， <xref:System.Object?displayProperty=nameWithType>，或枚举。  
  
 如果设计需要其他类型的参数，强重新评估是否 API 确实表示对逻辑集合取值函数。 如果不是，使用一种方法。 请考虑从开始使用的方法名称`Get`或`Set`。  
  
 **✓ DO** 使用名称`Item`的索引属性，除非有显然更好的名称 (例如，请参阅<xref:System.String.Chars%2A>属性`System.String`)。  
  
 在 C# 中，索引器的默认命名项。 <xref:System.Runtime.CompilerServices.IndexerNameAttribute>可用于自定义此名称。  
  
 **X DO NOT** 提供索引器和在语义上等效的方法。  
  
 **X DO NOT** 提供多个系列中一种类型的重载索引器。  
  
 C# 编译器强制这一点。  
  
 **X DO NOT** 使用非默认索引属性。  
  
 C# 编译器强制这一点。  
  
### <a name="property-change-notification-events"></a>属性更改通知事件  
 有时是可用于提供事件通知用户中的属性值的更改。 例如，`System.Windows.Forms.Control`将引发`TextChanged`的值之后的事件及其`Text`属性已更改。  
  
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
