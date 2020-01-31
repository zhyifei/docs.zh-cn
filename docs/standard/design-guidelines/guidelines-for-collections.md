---
title: 컬렉션에 대한 지침
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
# <a name="guidelines-for-collections"></a>컬렉션에 대한 지침
可将任何专门设计用于操作一组具有一些共同特征的对象的类型视为一个集合。 这些类型几乎总适合用于实现 <xref:System.Collections.IEnumerable> 或 <xref:System.Collections.Generic.IEnumerable%601>，因此在本节中，我们只将实现其中一个或两个接口的类型视为集合。

 ❌ 不要在公共 Api 中使用弱类型集合。

 表示集合项的所有返回值和参数的类型应该是确切的项类型，而不是其任何基类型（这仅适用于集合的公共成员）。

 ❌ 在公共 Api 中不使用 <xref:System.Collections.ArrayList> 或 <xref:System.Collections.Generic.List%601>。

 这些类型是设计用于内部实现而非公共 API 的数据结构。 `List<T>` 以 API 的清洁度和灵活性为代价，针对性能和功耗进行了优化。 例如，如果你返回 `List<T>`，则在客户端代码修改集合时，你无法接收通知。 此外，`List<T>` 公开了许多在许多情况下无用或不适用的成员（比如 <xref:System.Collections.Generic.List%601.BinarySearch%2A>）。 以下两节介绍了专门设计用于公共 API 的类型（抽象）。

 ❌ 在公共 Api 中不使用 `Hashtable` 或 `Dictionary<TKey,TValue>`。

 这些类型是设计用于内部实现的数据结构。 公共 API 应该使用 <xref:System.Collections.IDictionary>、`IDictionary <TKey, TValue>` 或实现两个接口其中之一或两者的自定义类型。

 ❌ 不使用任何实现这些接口的 <xref:System.Collections.Generic.IEnumerator%601>、<xref:System.Collections.IEnumerator>或任何其他类型，但 `GetEnumerator` 方法的返回类型除外。

 从 `GetEnumerator` 以外的方法返回枚举器的类型不能用于 `foreach` 语句。

 ❌ 不会在同一类型上同时实现 `IEnumerator<T>` 和 `IEnumerable<T>`。 这同样适用于非通用接口`IEnumerator`和`IEnumerable`。

## <a name="collection-parameters"></a>集合参数
 ✔️确实使用最小专用类型作为参数类型。 将集合作为参数的大多数成员使用 `IEnumerable<T>` 接口。

 ❌ 避免使用 <xref:System.Collections.Generic.ICollection%601> 或 <xref:System.Collections.ICollection> 作为参数，只是为了访问 `Count` 属性。

 而可考虑使用 `IEnumerable<T>` 或 `IEnumerable`，并动态地检查对象是实现了 `ICollection<T>` 还是 `ICollection`。

## <a name="collection-properties-and-return-values"></a>集合属性和返回值
 ❌ 不提供可设置的集合属性。

 用户可以先清除集合，然后添加新的内容，从而替换集合的内容。 如果替换整个集合是一种常见的情况，请考虑对该集合提供 `AddRange` 方法。

 ✔️确实要对表示读/写集合的属性或返回值使用 `Collection<T>` 或 `Collection<T>` 的子类。

 如果 `Collection<T>` 不符合某些要求（例如，集合不得实现 <xref:System.Collections.IList>），请通过实现 `IEnumerable<T>`、`ICollection<T>` 或 <xref:System.Collections.Generic.IList%601> 来使用自定义集合。

 ✔️使用 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>、`ReadOnlyCollection<T>`的子类或在极少数情况下 `IEnumerable<T>` 表示只读集合的属性或返回值。

 一般情况下，更倾向于使用 `ReadOnlyCollection<T>`。 如果它不符合某些要求（例如，集合不得实现 `IList`），请实现 `IEnumerable<T>`、`ICollection<T>` 或 `IList<T>` 来使用自定义集合。 如果实现了自定义只读集合，请实现 `ICollection<T>.IsReadOnly` 以返回 `true`。

 如果你确定唯一需提供支持的情况是仅正向迭代，则只需使用 `IEnumerable<T>` 即可。

 ✔️考虑使用泛型基集合的子类，而不是直接使用集合。

 通过此操作，可使用更好的名称并添加基本集合类型中不存在的辅助成员。 这尤其适用于高级 API。

 ✔️考虑从非常常用的方法和属性返回 `Collection<T>` 或 `ReadOnlyCollection<T>` 的子类。

 通过此操作，可在将来添加辅助方法或更改集合实现。

 ✔️如果集合中存储的项具有唯一键（名称、Id 等），请考虑使用键控集合。 键控集合是可以由整数和键索引的集合，通常通过继承自`KeyedCollection<TKey,TItem>` 进行实现。

 键控集合的内存占用通常较大，并且如果内存开销超过了使用键的益处，则不应使用键控集合。

 ❌ 不从集合属性或返回集合的方法中返回 null 值。 而应返回空集合或空数组。

 原则上，应将 null 和空（0 项）集合或数组视为相同。

### <a name="snapshots-versus-live-collections"></a>快照集合与实时集合
 表示某个时间点的状态的集合称为快照集合。 例如，包含从数据库查询返回的行的集合是快照集合。 始终表示当前状态的集合称为实时集合。 例如，`ComboBox` 项的集合就是一个实时集合。

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

 ✔️在设计新集合时实现 `IEnumerable<T>`。 当有需要时，考虑实现 `ICollection<T>` 甚至 `IList<T>`。

 在实现此类自定义集合时，请尽可能遵循 `Collection<T>` 和 `ReadOnlyCollection<T>` 建立的 API 模式。 也就是说，显式实现相同的成员，以及命名参数（与这两个集合命名它们的方式类似）等。

 ✔️如果集合经常传递到采用这些接口作为输入的 Api，则可考虑实现非泛型集合接口（`IList` 和 `ICollection`）。

 ❌ 避免使用与集合概念无关的复杂 Api 在类型上实现集合接口。

 ❌ 不从非泛型基集合继承，如 `CollectionBase`。 相反，使用 `Collection<T>`、`ReadOnlyCollection<T>` 和 `KeyedCollection<TKey,TItem>`。

### <a name="naming-custom-collections"></a>命名自定义集合
 创建集合（实现 `IEnumerable` 的类型）主要有两个原因：(1) 创建具有结构特定操作的新数据结构，并且通常具有与现有数据结构不同的性能特征（例如，<xref:System.Collections.Generic.List%601>、<xref:System.Collections.Generic.LinkedList%601>、<xref:System.Collections.Generic.Stack%601>） 以及 (2) 创建用于保存一组特定的项的专用的集合（例如，<xref:System.Collections.Specialized.StringCollection>）。 数据结构最常用于应用程序和库的内部实现。 专用集合主要在 API 中公开（作为属性和参数类型）。

 ✔️在实现 `IDictionary` 或 `IDictionary<TKey,TValue>`的抽象名称中使用 "Dictionary" 后缀。

 ✔️在实现 `IEnumerable` 的类型（或其任何子代）的名称中使用 "Collection" 后缀，并表示项列表。

 ✔️为自定义数据结构使用适当的数据结构名称。

 ❌ 避免使用任何后缀来指定集合抽象名称中的特定实现，如 "LinkedList" 或 "哈希表"。

 ✔️考虑为集合名称加上项类型的名称。 例如，存储类型为 `Address` 的项的集合（实现 `IEnumerable<Address>`）应该命名为 `AddressCollection`。 如果项类型是接口，则可以省略项类型的 “I” 前缀。 因此，<xref:System.IDisposable> 项的集合可以称为 `DisposableCollection`。

 如果可在框架中添加或已存在相应的可写集合，则✔️考虑在只读集合的名称中使用 "ReadOnly" 前缀。

 例如，只读字符串集合应称为 `ReadOnlyStringCollection`。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
