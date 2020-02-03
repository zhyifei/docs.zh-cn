---
title: 集合准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: 50497de6569b448ab036af8a1fbf76a47565e2bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741863"
---
# <a name="guidelines-for-collections"></a>集合准则
可将任何专门设计用于操作一组具有一些共同特征的对象的类型视为一个集合。 几乎始终适合这种类型 <xref:System.Collections.IEnumerable> 或 <xref:System.Collections.Generic.IEnumerable%601>实现，因此在本部分中，我们只考虑实现其中一个或两个接口都是集合的类型。

 ❌ 不要在公共 Api 中使用弱类型集合。

 表示集合项的所有返回值和参数的类型应该是确切的项类型，而不是其任何基类型（这仅适用于集合的公共成员）。

 ❌ 在公共 Api 中不使用 <xref:System.Collections.ArrayList> 或 <xref:System.Collections.Generic.List%601>。

 这些类型是设计用于内部实现而非公共 API 的数据结构。 `List<T>` 经过优化，可实现更高的性能和功能，同时 cleanness Api 和灵活性。 例如，如果你返回 `List<T>`，则当客户端代码修改集合时，你将不会收到通知。 此外，`List<T>` 公开许多成员，如 <xref:System.Collections.Generic.List%601.BinarySearch%2A>，这在许多情况下并不有用或适用。 以下两节介绍了专门设计用于公共 API 的类型（抽象）。

 ❌ 在公共 Api 中不使用 `Hashtable` 或 `Dictionary<TKey,TValue>`。

 这些类型是设计用于内部实现的数据结构。 公共 Api 应使用 <xref:System.Collections.IDictionary>、`IDictionary <TKey, TValue>`或实现一个或两个接口的自定义类型。

 ❌ 不使用任何实现这些接口的 <xref:System.Collections.Generic.IEnumerator%601>、<xref:System.Collections.IEnumerator>或任何其他类型，但 `GetEnumerator` 方法的返回类型除外。

 从 `GetEnumerator` 以外的方法返回枚举器的类型不能与 `foreach` 语句一起使用。

 ❌ 不会在同一类型上同时实现 `IEnumerator<T>` 和 `IEnumerable<T>`。 这同样适用于非泛型接口 `IEnumerator` 和 `IEnumerable`。

## <a name="collection-parameters"></a>集合参数
 ✔️确实使用最小专用类型作为参数类型。 将集合作为参数的大多数成员均使用 `IEnumerable<T>` 接口。

 ❌ 避免使用 <xref:System.Collections.Generic.ICollection%601> 或 <xref:System.Collections.ICollection> 作为参数，只是为了访问 `Count` 属性。

 请考虑使用 `IEnumerable<T>` 或 `IEnumerable` 并动态检查该对象是否实现 `ICollection<T>` 或 `ICollection`。

## <a name="collection-properties-and-return-values"></a>集合属性和返回值
 ❌ 不提供可设置的集合属性。

 用户可以先清除集合，然后添加新的内容，从而替换集合的内容。 如果替换整个集合是一个常见方案，请考虑在集合上提供 `AddRange` 方法。

 ✔️确实要对表示读/写集合的属性或返回值使用 `Collection<T>` 或 `Collection<T>` 的子类。

 如果 `Collection<T>` 不满足某些要求（例如，集合不得实现 <xref:System.Collections.IList>），则通过实现 `IEnumerable<T>`、`ICollection<T>`或 <xref:System.Collections.Generic.IList%601>来使用自定义集合。

 ✔️使用 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>、`ReadOnlyCollection<T>`的子类或在极少数情况下 `IEnumerable<T>` 表示只读集合的属性或返回值。

 通常情况下，首选 `ReadOnlyCollection<T>`。 如果它不满足某些要求（例如，集合不得实现 `IList`），请通过实现 `IEnumerable<T>`、`ICollection<T>`或 `IList<T>`来使用自定义集合。 如果实现自定义的只读集合，则实现 `ICollection<T>.IsReadOnly` 以返回 `true`。

 如果你确定要支持的唯一方案是只进迭代，只需使用 `IEnumerable<T>`即可。

 ✔️考虑使用泛型基集合的子类，而不是直接使用集合。

 通过此操作，可使用更好的名称并添加基本集合类型中不存在的辅助成员。 这尤其适用于高级 API。

 ✔️考虑从非常常用的方法和属性返回 `Collection<T>` 或 `ReadOnlyCollection<T>` 的子类。

 通过此操作，可在将来添加辅助方法或更改集合实现。

 ✔️如果集合中存储的项具有唯一键（名称、Id 等），请考虑使用键控集合。 键控集合是可以由整数和密钥编制索引的集合，通常通过继承 `KeyedCollection<TKey,TItem>`来实现。

 键控集合的内存占用通常较大，并且如果内存开销超过了使用键的益处，则不应使用键控集合。

 ❌ 不从集合属性或返回集合的方法中返回 null 值。 而应返回空集合或空数组。

 原则上，应将 null 和空（0 项）集合或数组视为相同。

### <a name="snapshots-versus-live-collections"></a>快照集合与实时集合
 表示某个时间点的状态的集合称为快照集合。 例如，包含从数据库查询返回的行的集合是快照集合。 始终表示当前状态的集合称为实时集合。 例如，`ComboBox` 项的集合为活动集合。

 ❌ 不从属性返回快照集合。 属性应返回实时集合。

 属性 getter 应该是非常轻量级的操作。 返回快照需要在 O(n) 操作中创建内部集合的副本。

 ✔️使用快照集合或实时 `IEnumerable<T>` （或其子类型）来表示可变的集合（即，在未显式修改集合的情况下可以更改）。

 一般情况下，表示共享资源（例如，目录中的文件）的所有集合都是易失集合。 此类集合很难或不可能作为实时集合实现，除非该实现只是一个仅正向枚举器。

## <a name="choosing-between-arrays-and-collections"></a>在数组和集合之间进行选择
 ✔️是否比数组更倾向于集合。

 集合提供了对内容的更多控制，可以随着时间的推移而发展，并且可用性更好。 此外，不鼓励将数组用于只读场景，因为克隆数组的成本过高。 可用性研究表明，一些开发人员更习惯使用基于集合的 API。

 但是，如果你正在开发低级 API，则对读写场景使用数组可能会更好。 数组的内存占用较小，这有助于减少工作集，并且对数组中元素的访问速度更快，因为它通过运行时进行了优化。

 ✔️考虑在低级别 Api 中使用数组，以最大程度地减少内存占用和最大化性能。

 ✔️使用字节数组而不是字节集合。

 如果属性需要在每次调用属性 getter 时返回新数组（例如，内部数组的副本），则 ❌ 不使用属性的数组。

## <a name="implementing-custom-collections"></a>实现自定义集合
 ✔️考虑在设计新集合时从 `Collection<T>`、`ReadOnlyCollection<T>`或 `KeyedCollection<TKey,TItem>` 继承。

 ✔️在设计新集合时实现 `IEnumerable<T>`。 请考虑实现 `ICollection<T>` 甚至 `IList<T>`。

 实现此类自定义集合时，请遵循 `Collection<T>` 和 `ReadOnlyCollection<T>` 建立的 API 模式。 也就是说，显式实现相同的成员，以及命名参数（与这两个集合命名它们的方式类似）等。

 ✔️如果集合经常传递到采用这些接口作为输入的 Api，则可考虑实现非泛型集合接口（`IList` 和 `ICollection`）。

 ❌ 避免使用与集合概念无关的复杂 Api 在类型上实现集合接口。

 ❌ 不从非泛型基集合继承，如 `CollectionBase`。 改为使用 `Collection<T>`、`ReadOnlyCollection<T>`和 `KeyedCollection<TKey,TItem>`。

### <a name="naming-custom-collections"></a>命名自定义集合
 创建集合（实现 `IEnumerable`的类型）主要有两个原因：（1）若要创建一个具有特定结构的操作的新数据结构，并且通常与现有数据结构（例如，<xref:System.Collections.Generic.List%601>、<xref:System.Collections.Generic.LinkedList%601>、<xref:System.Collections.Generic.Stack%601>）具有不同的性能特征，请使用（2）创建用于保存一组特定项（例如，<xref:System.Collections.Specialized.StringCollection>）的专用集合。 数据结构最常用于应用程序和库的内部实现。 专用集合主要在 API 中公开（作为属性和参数类型）。

 ✔️在实现 `IDictionary` 或 `IDictionary<TKey,TValue>`的抽象名称中使用 "Dictionary" 后缀。

 ✔️在实现 `IEnumerable` 的类型（或其任何子代）的名称中使用 "Collection" 后缀，并表示项列表。

 ✔️为自定义数据结构使用适当的数据结构名称。

 ❌ 避免使用任何后缀来指定集合抽象名称中的特定实现，如 "LinkedList" 或 "哈希表"。

 ✔️考虑为集合名称加上项类型的名称。 例如，存储类型 `Address` （实现 `IEnumerable<Address>`）的项的集合应命名为 `AddressCollection`。 如果项类型是接口，则可以省略项类型的 “I” 前缀。 因此，可以 `DisposableCollection`调用 <xref:System.IDisposable> 项的集合。

 如果可在框架中添加或已存在相应的可写集合，则✔️考虑在只读集合的名称中使用 "ReadOnly" 前缀。

 例如，应 `ReadOnlyStringCollection`调用字符串的只读集合。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
