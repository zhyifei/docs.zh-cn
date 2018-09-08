---
title: 集合准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3571ebb2fdd2bcdfd8be1f0087d096e01f18790a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44128951"
---
# <a name="guidelines-for-collections"></a>集合准则
任何专门用于操作的一组具有一些公共特征的对象的类型可被视为集合。 它几乎总是适合于此类类型来实现<xref:System.Collections.IEnumerable>或<xref:System.Collections.Generic.IEnumerable%601>，因此在本部分中我们只考虑实现一个或两个这些接口的类型是集合。  
  
 **X DO NOT** 公共 api 使用弱类型的集合。  
  
 所有返回值和参数表示的收集项的类型应为确切项类型，不是任何基类型 （这仅适用于集合中的公共成员）。  
  
 **X DO NOT** 使用<xref:System.Collections.ArrayList>或<xref:System.Collections.Generic.List%601>公共 Api 中。  
  
 这些类型是设计用于在内部实现中，不在公共 Api 中的数据结构。 `List<T>` 已针对性能和但代价是 cleanness 的 Api 和灵活性的电源优化。 例如，如果您返回`List<T>`，曾经无法接收通知，当客户端代码将修改的集合。 此外，`List<T>`公开很多成员，如<xref:System.Collections.Generic.List%601.BinarySearch%2A>，不是很有用，或在许多情况下适用。 以下两个部分介绍专门设计用于在公共 Api 中的类型 （抽象）。  
  
 **X DO NOT** 使用`Hashtable`或`Dictionary<TKey,TValue>`公共 Api 中。  
  
 这些类型是设计用于在内部实现中使用的数据结构。 应使用公共 Api <xref:System.Collections.IDictionary>， `IDictionary <TKey, TValue>`，或实现一个或两个接口的自定义类型。  
  
 **X DO NOT** 使用<xref:System.Collections.Generic.IEnumerator%601>， <xref:System.Collections.IEnumerator>，或实现这些接口，任一除用作返回类型的任何其他类型`GetEnumerator`方法。  
  
 不从方法返回枚举器的类型`GetEnumerator`不能用于`foreach`语句。  
  
 **X DO NOT** 实现`IEnumerator<T>`和`IEnumerable<T>`上相同的类型。 这同样适用于非泛型接口`IEnumerator`和`IEnumerable`。  
  
## <a name="collection-parameters"></a>收集参数  
 **✓ DO** 作为参数类型使用的最小专用类型可能。 执行集合的参数使用的大多数成员`IEnumerable<T>`接口。  
  
 **X AVOID** 使用<xref:System.Collections.Generic.ICollection%601>或<xref:System.Collections.ICollection>作为参数只是为了访问`Count`属性。  
  
 相反，请考虑使用`IEnumerable<T>`或`IEnumerable`和动态检查该对象是否实现`ICollection<T>`或`ICollection`。  
  
## <a name="collection-properties-and-return-values"></a>集合属性和返回值  
 **X DO NOT** 提供可设置的集合属性。  
  
 用户可以通过先清除集合，然后添加新的内容替换该集合的内容。 如果将替换整个集合作为一种常见方案，请考虑提供`AddRange`集合方法。  
  
 **✓ DO** 使用`Collection<T>`或的子类`Collection<T>`为属性或返回值表示的读/写集合。  
  
 如果`Collection<T>`不符合某些要求 (例如，集合必须实现<xref:System.Collections.IList>)，通过实现使用自定义集合`IEnumerable<T>`， `ICollection<T>`，或<xref:System.Collections.Generic.IList%601>。  
  
 **✓ DO** 使用<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>的一个子类`ReadOnlyCollection<T>`，或在极少数情况下`IEnumerable<T>`为属性或返回值表示的只读集合。  
  
 一般情况下，更喜欢`ReadOnlyCollection<T>`。 如果不满足某些需求 (例如，集合必须实现`IList`)，通过实现使用自定义集合`IEnumerable<T>`， `ICollection<T>`，或`IList<T>`。 如果您实现自定义的只读集合，实现`ICollection<T>.IsReadOnly`以返回`true`。  
  
 在其中你确信将想要支持的唯一方案是只进迭代的情况下，您可以直接使用`IEnumerable<T>`。  
  
 **✓ CONSIDER** 而不直接使用集合使用泛型基集合的子类。  
  
 这样更好的名称以及添加基集合类型不存在的帮助器成员。 此选项特别适用于高级 Api。  
  
 **✓ CONSIDER** 返回的一个子类`Collection<T>`或`ReadOnlyCollection<T>`从非常常用的方法和属性。  
  
 这将使您可以添加帮助器方法或更改在将来的集合实现。  
  
 **✓ CONSIDER** 使用键控的集合，如果在集合中存储的项具有唯一键 （名称、 Id，等等。）。 键控的集合是集合可以建立索引的一个整数和一个密钥并通常通过继承实现`KeyedCollection<TKey,TItem>`。  
  
 键控的集合通常较大内存需求量，并且不应在内存开销远远超过拥有密钥的好处。  
  
 **X DO NOT** 返回 null 值，从集合属性或方法返回集合。 而是返回一个空集合或一个空数组。  
  
 一般规则是应为 null 和空 （0 项） 集合或数组的处理相同。  
  
### <a name="snapshots-versus-live-collections"></a>与实时集合的快照  
 表示的时间在某个时间点的状态的集合都称为快照集合。 例如，包含从数据库查询返回行的集合将快照。 始终表示的当前状态的集合都称为实时的集合。 例如，集合`ComboBox`项是实时的集合。  
  
 **X DO NOT** 从属性中返回快照集合。 属性应返回实时的集合。  
  
 属性 getter 应非常轻量的操作。 返回快照需要 o （n） 操作中创建内部集合的副本。  
  
 **✓ DO** 使用快照集合或实时`IEnumerable<T>`（或其子类型） 来表示是易失性的集合 （即，可以更改而无需显式修改集合）。  
  
 一般情况下，所有集合表示共享的资源 （例如，在目录中的文件） 都是易失性的。 此类集合是很难或不可能实现作为实时的集合，除非实现是只是一个只进的枚举器。  
  
## <a name="choosing-between-arrays-and-collections"></a>数组和集合之间进行选择  
 **✓ DO** 更愿意集合，而数组。  
  
 集合提供更好地控制内容，可以随时间而并且更易于使用。 此外，数组的只读的情况下不建议使用，因为克隆该数组的成本很高的磁盘。 可用性研究表明，一些开发人员更喜欢使用基于集合的 Api。  
  
 但是，如果你正在开发低级别 Api，它可能是更好的做法数组用于读写方案。 数组具有更小的内存空间，这有助于减少工作集，并对数组中元素的访问会提高，因为它由运行时进行了优化。  
  
 **✓ CONSIDER** 在低级别 Api 中使用数组最大程度减少内存占用和最大程度提高性能。  
  
 **✓ DO** 使用而不是集合的字节的字节数组。  
  
 **X DO NOT** 用于属性的数组，如果该属性需要调用属性 getter 每次返回一个新数组 （例如，内部数组的副本）。  
  
## <a name="implementing-custom-collections"></a>实现自定义集合  
 **✓ CONSIDER** 继承自`Collection<T>`， `ReadOnlyCollection<T>` ，或`KeyedCollection<TKey,TItem>`设计新的集合时。  
  
 **✓ DO** 实现`IEnumerable<T>`设计新的集合时。 请考虑实施`ICollection<T>`甚至`IList<T>`非常有用。  
  
 在实现此类自定义集合时，遵循 API 模式建立`Collection<T>`和`ReadOnlyCollection<T>`尽可能接近。 即，显式实现相同的成员，如这两个集合命名它们，并因此在命名参数。  
  
 **✓ CONSIDER** 实现非泛型集合接口 (`IList`和`ICollection`) 如果该集合将通常会传递给 Api 采用这些接口作为输入。  
  
 **X AVOID** 在类型中的集合接口实现的复杂且不与集合中的这一概念相关的 Api。  
  
 **X DO NOT** 如继承自非泛型基集合`CollectionBase`。 使用`Collection<T>`， `ReadOnlyCollection<T>`，和`KeyedCollection<TKey,TItem>`相反。  
  
### <a name="naming-custom-collections"></a>命名自定义集合  
 集合 (类型实现`IEnumerable`) 创建主要有两个原因: (1) 若要创建新的数据结构与特定于结构的操作，通常不同的性能特征与现有数据结构 (例如， <xref:System.Collections.Generic.List%601>，<xref:System.Collections.Generic.LinkedList%601>， <xref:System.Collections.Generic.Stack%601>)，和 (2) 若要创建用于保存一组特定的项的专用的集合 (例如， <xref:System.Collections.Specialized.StringCollection>)。 在应用程序和库的内部实现最常使用的数据结构。 专用的集合是主要是为了在 （作为属性和参数类型） 的 Api 中公开。  
  
 **✓ DO** 实现的抽象名称中使用"字典"后缀`IDictionary`或`IDictionary<TKey,TValue>`。  
  
 **✓ DO** 在实现的类型的名称中使用"集合"后缀`IEnumerable`（或其任意后代） 和表示的项的列表。  
  
 **✓ DO** 使用自定义数据结构的适当的数据结构名称。  
  
 **X AVOID** 的集合的抽象的名称中使用并暗示特定实现，如"LinkedList"或"哈希表，"任何后缀。  
  
 **✓ CONSIDER** 前缀同名的项类型的集合名称。 例如，存储类型的项的集合`Address`(实施`IEnumerable<Address>`) 应命名为`AddressCollection`。 如果项类型是接口，"I"前缀的项的类型，则可以省略。 因此，集合<xref:System.IDisposable>可调用项`DisposableCollection`。  
  
 **✓ CONSIDER** 如果相应的可写集合可能添加或已存在 framework 中的只读集合的名称中使用"ReadOnly"前缀。  
  
 例如，应调用一个只读字符串集合`ReadOnlyStringCollection`。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
