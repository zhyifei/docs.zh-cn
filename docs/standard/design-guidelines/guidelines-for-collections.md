---
title: 集合准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3571ebb2fdd2bcdfd8be1f0087d096e01f18790a
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964825"
---
# <a name="guidelines-for-collections"></a>集合准则
任何专门设计用于操作具有一些共同特征的一组对象的类型都可以被认为是集合。这些类型几乎总是适合实现<xref:System.Collections.IEnumerable> 或 <xref:System.Collections.Generic.IEnumerable%601>，因此在本部分中，我们只将实现了这些接口中的一个或两个的类型认为是集合。
  
**X 切忌** 在公共 API 中使用弱类型的集合。  

表示集合项的所有返回值和参数的类型应该是确切的项类型，而不是其任何基类型（这仅适用于集合的公共成员）。
  
**X 切忌** 在公共 API 中使用 <xref:System.Collections.ArrayList> 或 <xref:System.Collections.Generic.List%601>。

这些类型是设计用于内部实现的数据结构，而不是用于公共 API。 `List<T>` 以 API 的清洁度和灵活性为代价，针对性能和功耗进行了优化。例如，如果您返回 `List<T>`，当客户端代码修改集合时，您将无法接收通知。还有，`List<T>` 暴露了很多成员，比如 <xref:System.Collections.Generic.List%601.BinarySearch%2A> ，在许多场景中不是很有用或不适用。以下两个部分介绍了专门为公共 API 设计的类型（抽象）。
  
**X 切忌** 在公共 Api 中使用 `Hashtable` 或 `Dictionary<TKey,TValue>`。  

这些类型是设计用于内部实现的数据结构。公共 API 应该使用 <xref:System.Collections.IDictionary>，`IDictionary<TKey, TValue>`，或实现这些一个或两个接口的自定义类型。
  
**X 切忌** 使用 <xref:System.Collections.Generic.IEnumerator%601>， <xref:System.Collections.IEnumerator>，或实现这些接口之一的任何其他类型，除了作为 `GetEnumerator` 方法的返回类型。

从 `GetEnumerator` 以外的方法返回枚举器的类型不能用于 `foreach` 语句。
  
**X 切忌** 在同一类型上实现 `IEnumerator<T>` 和 `IEnumerable<T>`。 这同样适用于非泛型接口 `IEnumerator` 和 `IEnumerable`。  
  
## <a name="collection-parameters"></a>集合参数
**✓ 务必** 尽可能不将特定类型作为参数类型。将集合作为参数的大多数成员使用 `IEnumerable<T>` 接口。
  
**X 避免** 仅为了访问 `Count` 属性而使用 <xref:System.Collections.Generic.ICollection%601> 或<xref:System.Collections.ICollection> 作为参数。  
  
相反，请考虑使用 `IEnumerable<T>` 或 `IEnumerable` 并动态检查对象是否实现了 `ICollection<T>`或 `ICollection`。
  
## <a name="collection-properties-and-return-values"></a>集合属性和返回值
**X 切忌** 提供可设置的集合属性。  

用户可以先清除集合，然后添加新内容，以替换集合的内容。如果替换整个集合是一种常见的情况，请考虑在集合上提供 `AddRange` 方法。

**✓ 务必** 为表示读/写集合的属性或返回值使用 `Collection<T>` 或 `Collection<T>` 的子类。

如果 `Collection<T>` 不符合某些要求 (例如，集合不能实现 <xref:System.Collections.IList>)，请通过实现 `IEnumerable<T>`、`ICollection<T>` 或 <xref:System.Collections.Generic.IList%601> 使用自定义集合。

**✓ 务必** 为表示只读集合的​​属性或返回值使用 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>、`ReadOnlyCollection<T>` 的子类，或在极少数情况下使用 `IEnumerable<T>`。  

通常，更倾向使用 `ReadOnlyCollection<T>`。如果它不符合某些要求（例如，集合不能实现 `IList`），请通过实现`IEnumerable<T>`、`ICollection<T>` 或 `IList<T>` 来使用自定义集合。如果您实现了自定义只读集合，请实现`ICollection<T>.IsReadOnly` 以返回 `true`。

如果您确定您希望支持的唯一场景是仅向前迭代，可以简单地使用 `IEnumerable<T>`。

**✓ 考虑** 使用泛型基本集合的子类而不是直接使用集合。  

这允许使用更好的名称以及添加基本集合类型中不存在的辅助成员。这尤其适用于高级 API。

**✓ 考虑** 从非常常用的方法和属性返回 `Collection<T>` 或 `ReadOnlyCollection<T>` 的子类。  

这将使您可以在将来添加辅助方法或更改集合实现。  
  
**✓ 考虑** 如果存储在集合中的项目具有唯一键（名称，ID等），则使用键控集合。键控集合是可以通过整数和键索引的集合，通常通过继承自 `KeyedCollection<TKey,TItem>` 来实现。

键控的集合通常具有较大内存占用，如果内存开销超过使用键的益处，则不应使用。

**X 切忌** 从集合属性或返回集合的方法返回 null 值。应返回一个空集合或一个空数组。

一般规则是 null 和 空（0 项）集合或数组应该被视为相同。
  
### <a name="snapshots-versus-live-collections"></a>快照与实时集合
在某个时间点表示状态的集合称为快照集合。例如，包含从数据库查询返回的行的集合将是快照。始终表示当前状态的集合称为实时集合。例如，`ComboBox` 项的集合是一个实时集合。

**X 不要** 从属性中返回快照集合。属性应返回实时集合。

属性 getter 应该是非常轻量级的操作。返回快照需要在 O(n) 操作中创建内部集合的副本。
  
**✓ 务必** 使用快照集合或实时 `IEnumerable<T>`（或其子类型）表示易变集合（即，可以在没有明确修改集合的情况下进行更改）。

一般情况下，表示共享资源（例如，目录中的文件）的所有集合都是易变的。除非实现只是一个只进的枚举器，否则这些集合很难或不可能作为实时集合实现。

## <a name="choosing-between-arrays-and-collections"></a>在数组和集合之间进行选择
**✓ 务必** 更倾向使用集合，而不是数组。

集合提供了对内容的更多控制，可以随着时间的推移而发展，并且更加可用。此外，不鼓励将数组用于只读方案，因为克隆数组的成本过高。可用性研究表明，一些开发人员更习惯使用基于集合的API。

但是，如果您正在开发低级 API，那么将数组用于读写方案可能会更好。数组的内存占用量较小，这有助于减少工作集，并且对数组中元素的访问速度更快，因为它是由运行时优化的。
  
**✓ 考虑** 在低级别 API 中使用数组，以最大程度地减少内存消耗并最大程度地提高性能。

**✓ 务必** 使用字节数组而不是字节集合。  
 
**X 切忌** 使用数组作为属性，如果属性在每次调用属性 getter 时都必须返回一个新数组（例如，内部数组的副本）。  
  
## <a name="implementing-custom-collections"></a>实现自定义集合
**✓ 考虑** 在设计新集合时，从 `Collection<T>`、`ReadOnlyCollection<T>` 或 `KeyedCollection<TKey,TItem>` 继承。  

**✓ 务必** 在设计新集合时，实现 `IEnumerable<T>`。当有需要时，考虑实现 `ICollection<T>` 甚至 `IList<T>`。

在实现此类自定义集合时，请尽可能遵循 `Collection<T>` 和 `ReadOnlyCollection<T>` 建立的 API 模式。也就是说，显式实现相同的成员，像这两个集合命名它们一样来命名参数，等等。 

**✓ 考虑** 实现非泛型集合接口（`IList` 和 `ICollection`），如果该集合经常被传递给以这些接口为输入的 API。  

**X 避免** 在具有与集合概念无关的复杂 API 的类型上实现集合接口。

**X 切忌** 从非泛型基本集合继承，如 `CollectionBase`。相反，使用 `Collection<T>`、`ReadOnlyCollection<T>` 和 `KeyedCollection<TKey,TItem>`。
  
### <a name="naming-custom-collections"></a>命名自定义集合
创建集合（实现 `IEnumerable` 的类型）主要有两个原因：(1) 创建具有特定结构操作的新数据结构，并且通常具有与现有数据结构不同的性能特征（例如，<xref:System.Collections.Generic.List%601>，<xref:System.Collections.Generic.LinkedList%601>， <xref:System.Collections.Generic.Stack%601>），以及 (2) 创建用于保存一组特定的项的专用的集合（例如，<xref:System.Collections.Specialized.StringCollection>）。数据结构最常用于应用程序和库的内部实现。专用集合主要在 API 中公开（作为属性和参数类型）。

**✓ 务必** 在实现 `IDictionary` 或 `IDictionary<TKey,TValue>` 的抽象名称中使用 “Dictionary” 后缀。

**✓ 务必** 在实现 `IEnumerable`（或其任意后代）的类型名称中使用 “Collection” 后缀并表示项的列表。  

**✓ 务必** 为自定义数据结构使用适当的数据结构名称。

**X 避免** 在集合抽象名称中使用任何暗示特定实现的后缀，例如 “LinkedList” 或 “Hashtable”。

**✓ 考虑** 在集合名称前加上项类型的名称。例如，一个存储类型为 `Address` 的项的集合（实现 `IEnumerable<Address>`）应该命名为 `AddressCollection`。如果项类型是接口，则可以省略项类型的 “I” 前缀。因此，一个 <xref:System.IDisposable> 项的集合可以称为 `DisposableCollection`。

**✓ 考虑** 如果可能在框架中添加或已存在相应的可写集合，则在只读集合的​​名称中使用 “ReadOnly” 前缀。

例如，一个只读字符串集合应称为 `ReadOnlyStringCollection`。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  

*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*

## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
