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
# <a name="guidelines-for-collections"></a><span data-ttu-id="79b32-102">集合准则</span><span class="sxs-lookup"><span data-stu-id="79b32-102">Guidelines for Collections</span></span>
<span data-ttu-id="79b32-103">可将任何专门设计用于操作一组具有一些共同特征的对象的类型视为一个集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-103">Any type designed specifically to manipulate a group of objects having some common characteristic can be considered a collection.</span></span> <span data-ttu-id="79b32-104">几乎始终适合这种类型 <xref:System.Collections.IEnumerable> 或 <xref:System.Collections.Generic.IEnumerable%601>实现，因此在本部分中，我们只考虑实现其中一个或两个接口都是集合的类型。</span><span class="sxs-lookup"><span data-stu-id="79b32-104">It is almost always appropriate for such types to implement <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601>, so in this section we only consider types implementing one or both of those interfaces to be collections.</span></span>

 <span data-ttu-id="79b32-105">❌ 不要在公共 Api 中使用弱类型集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-105">❌ DO NOT use weakly typed collections in public APIs.</span></span>

 <span data-ttu-id="79b32-106">表示集合项的所有返回值和参数的类型应该是确切的项类型，而不是其任何基类型（这仅适用于集合的公共成员）。</span><span class="sxs-lookup"><span data-stu-id="79b32-106">The type of all return values and parameters representing collection items should be the exact item type, not any of its base types (this applies only to public members of the collection).</span></span>

 <span data-ttu-id="79b32-107">❌ 在公共 Api 中不使用 <xref:System.Collections.ArrayList> 或 <xref:System.Collections.Generic.List%601>。</span><span class="sxs-lookup"><span data-stu-id="79b32-107">❌ DO NOT use <xref:System.Collections.ArrayList> or <xref:System.Collections.Generic.List%601> in public APIs.</span></span>

 <span data-ttu-id="79b32-108">这些类型是设计用于内部实现而非公共 API 的数据结构。</span><span class="sxs-lookup"><span data-stu-id="79b32-108">These types are data structures designed to be used in internal implementation, not in public APIs.</span></span> <span data-ttu-id="79b32-109">`List<T>` 经过优化，可实现更高的性能和功能，同时 cleanness Api 和灵活性。</span><span class="sxs-lookup"><span data-stu-id="79b32-109">`List<T>` is optimized for performance and power at the cost of cleanness of the APIs and flexibility.</span></span> <span data-ttu-id="79b32-110">例如，如果你返回 `List<T>`，则当客户端代码修改集合时，你将不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="79b32-110">For example, if you return `List<T>`, you will not ever be able to receive notifications when client code modifies the collection.</span></span> <span data-ttu-id="79b32-111">此外，`List<T>` 公开许多成员，如 <xref:System.Collections.Generic.List%601.BinarySearch%2A>，这在许多情况下并不有用或适用。</span><span class="sxs-lookup"><span data-stu-id="79b32-111">Also, `List<T>` exposes many members, such as <xref:System.Collections.Generic.List%601.BinarySearch%2A>, that are not useful or applicable in many scenarios.</span></span> <span data-ttu-id="79b32-112">以下两节介绍了专门设计用于公共 API 的类型（抽象）。</span><span class="sxs-lookup"><span data-stu-id="79b32-112">The following two sections describe types (abstractions) designed specifically for use in public APIs.</span></span>

 <span data-ttu-id="79b32-113">❌ 在公共 Api 中不使用 `Hashtable` 或 `Dictionary<TKey,TValue>`。</span><span class="sxs-lookup"><span data-stu-id="79b32-113">❌ DO NOT use `Hashtable` or `Dictionary<TKey,TValue>` in public APIs.</span></span>

 <span data-ttu-id="79b32-114">这些类型是设计用于内部实现的数据结构。</span><span class="sxs-lookup"><span data-stu-id="79b32-114">These types are data structures designed to be used in internal implementation.</span></span> <span data-ttu-id="79b32-115">公共 Api 应使用 <xref:System.Collections.IDictionary>、`IDictionary <TKey, TValue>`或实现一个或两个接口的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="79b32-115">Public APIs should use <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, or a custom type implementing one or both of the interfaces.</span></span>

 <span data-ttu-id="79b32-116">❌ 不使用任何实现这些接口的 <xref:System.Collections.Generic.IEnumerator%601>、<xref:System.Collections.IEnumerator>或任何其他类型，但 `GetEnumerator` 方法的返回类型除外。</span><span class="sxs-lookup"><span data-stu-id="79b32-116">❌ DO NOT use <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, or any other type that implements either of these interfaces, except as the return type of a `GetEnumerator` method.</span></span>

 <span data-ttu-id="79b32-117">从 `GetEnumerator` 以外的方法返回枚举器的类型不能与 `foreach` 语句一起使用。</span><span class="sxs-lookup"><span data-stu-id="79b32-117">Types returning enumerators from methods other than `GetEnumerator` cannot be used with the `foreach` statement.</span></span>

 <span data-ttu-id="79b32-118">❌ 不会在同一类型上同时实现 `IEnumerator<T>` 和 `IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="79b32-118">❌ DO NOT implement both `IEnumerator<T>` and `IEnumerable<T>` on the same type.</span></span> <span data-ttu-id="79b32-119">这同样适用于非泛型接口 `IEnumerator` 和 `IEnumerable`。</span><span class="sxs-lookup"><span data-stu-id="79b32-119">The same applies to the nongeneric interfaces `IEnumerator` and `IEnumerable`.</span></span>

## <a name="collection-parameters"></a><span data-ttu-id="79b32-120">集合参数</span><span class="sxs-lookup"><span data-stu-id="79b32-120">Collection Parameters</span></span>
 <span data-ttu-id="79b32-121">✔️确实使用最小专用类型作为参数类型。</span><span class="sxs-lookup"><span data-stu-id="79b32-121">✔️ DO use the least-specialized type possible as a parameter type.</span></span> <span data-ttu-id="79b32-122">将集合作为参数的大多数成员均使用 `IEnumerable<T>` 接口。</span><span class="sxs-lookup"><span data-stu-id="79b32-122">Most members taking collections as parameters use the `IEnumerable<T>` interface.</span></span>

 <span data-ttu-id="79b32-123">❌ 避免使用 <xref:System.Collections.Generic.ICollection%601> 或 <xref:System.Collections.ICollection> 作为参数，只是为了访问 `Count` 属性。</span><span class="sxs-lookup"><span data-stu-id="79b32-123">❌ AVOID using <xref:System.Collections.Generic.ICollection%601> or <xref:System.Collections.ICollection> as a parameter just to access the `Count` property.</span></span>

 <span data-ttu-id="79b32-124">请考虑使用 `IEnumerable<T>` 或 `IEnumerable` 并动态检查该对象是否实现 `ICollection<T>` 或 `ICollection`。</span><span class="sxs-lookup"><span data-stu-id="79b32-124">Instead, consider using `IEnumerable<T>` or `IEnumerable` and dynamically checking whether the object implements `ICollection<T>` or `ICollection`.</span></span>

## <a name="collection-properties-and-return-values"></a><span data-ttu-id="79b32-125">集合属性和返回值</span><span class="sxs-lookup"><span data-stu-id="79b32-125">Collection Properties and Return Values</span></span>
 <span data-ttu-id="79b32-126">❌ 不提供可设置的集合属性。</span><span class="sxs-lookup"><span data-stu-id="79b32-126">❌ DO NOT provide settable collection properties.</span></span>

 <span data-ttu-id="79b32-127">用户可以先清除集合，然后添加新的内容，从而替换集合的内容。</span><span class="sxs-lookup"><span data-stu-id="79b32-127">Users can replace the contents of the collection by clearing the collection first and then adding the new contents.</span></span> <span data-ttu-id="79b32-128">如果替换整个集合是一个常见方案，请考虑在集合上提供 `AddRange` 方法。</span><span class="sxs-lookup"><span data-stu-id="79b32-128">If replacing the whole collection is a common scenario, consider providing the `AddRange` method on the collection.</span></span>

 <span data-ttu-id="79b32-129">✔️确实要对表示读/写集合的属性或返回值使用 `Collection<T>` 或 `Collection<T>` 的子类。</span><span class="sxs-lookup"><span data-stu-id="79b32-129">✔️ DO use `Collection<T>` or a subclass of `Collection<T>` for properties or return values representing read/write collections.</span></span>

 <span data-ttu-id="79b32-130">如果 `Collection<T>` 不满足某些要求（例如，集合不得实现 <xref:System.Collections.IList>），则通过实现 `IEnumerable<T>`、`ICollection<T>`或 <xref:System.Collections.Generic.IList%601>来使用自定义集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-130">If `Collection<T>` does not meet some requirement (e.g., the collection must not implement <xref:System.Collections.IList>), use a custom collection by implementing `IEnumerable<T>`, `ICollection<T>`, or <xref:System.Collections.Generic.IList%601>.</span></span>

 <span data-ttu-id="79b32-131">✔️使用 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>、`ReadOnlyCollection<T>`的子类或在极少数情况下 `IEnumerable<T>` 表示只读集合的属性或返回值。</span><span class="sxs-lookup"><span data-stu-id="79b32-131">✔️ DO use <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, a subclass of `ReadOnlyCollection<T>`, or in rare cases `IEnumerable<T>` for properties or return values representing read-only collections.</span></span>

 <span data-ttu-id="79b32-132">通常情况下，首选 `ReadOnlyCollection<T>`。</span><span class="sxs-lookup"><span data-stu-id="79b32-132">In general, prefer `ReadOnlyCollection<T>`.</span></span> <span data-ttu-id="79b32-133">如果它不满足某些要求（例如，集合不得实现 `IList`），请通过实现 `IEnumerable<T>`、`ICollection<T>`或 `IList<T>`来使用自定义集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-133">If it does not meet some requirement (e.g., the collection must not implement `IList`), use a custom collection by implementing `IEnumerable<T>`, `ICollection<T>`, or `IList<T>`.</span></span> <span data-ttu-id="79b32-134">如果实现自定义的只读集合，则实现 `ICollection<T>.IsReadOnly` 以返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="79b32-134">If you do implement a custom read-only collection, implement `ICollection<T>.IsReadOnly` to return `true`.</span></span>

 <span data-ttu-id="79b32-135">如果你确定要支持的唯一方案是只进迭代，只需使用 `IEnumerable<T>`即可。</span><span class="sxs-lookup"><span data-stu-id="79b32-135">In cases where you are sure that the only scenario you will ever want to support is forward-only iteration, you can simply use `IEnumerable<T>`.</span></span>

 <span data-ttu-id="79b32-136">✔️考虑使用泛型基集合的子类，而不是直接使用集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-136">✔️ CONSIDER using subclasses of generic base collections instead of using the collections directly.</span></span>

 <span data-ttu-id="79b32-137">通过此操作，可使用更好的名称并添加基本集合类型中不存在的辅助成员。</span><span class="sxs-lookup"><span data-stu-id="79b32-137">This allows for a better name and for adding helper members that are not present on the base collection types.</span></span> <span data-ttu-id="79b32-138">这尤其适用于高级 API。</span><span class="sxs-lookup"><span data-stu-id="79b32-138">This is especially applicable to high-level APIs.</span></span>

 <span data-ttu-id="79b32-139">✔️考虑从非常常用的方法和属性返回 `Collection<T>` 或 `ReadOnlyCollection<T>` 的子类。</span><span class="sxs-lookup"><span data-stu-id="79b32-139">✔️ CONSIDER returning a subclass of `Collection<T>` or `ReadOnlyCollection<T>` from very commonly used methods and properties.</span></span>

 <span data-ttu-id="79b32-140">通过此操作，可在将来添加辅助方法或更改集合实现。</span><span class="sxs-lookup"><span data-stu-id="79b32-140">This will make it possible for you to add helper methods or change the collection implementation in the future.</span></span>

 <span data-ttu-id="79b32-141">✔️如果集合中存储的项具有唯一键（名称、Id 等），请考虑使用键控集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-141">✔️ CONSIDER using a keyed collection if the items stored in the collection have unique keys (names, IDs, etc.).</span></span> <span data-ttu-id="79b32-142">键控集合是可以由整数和密钥编制索引的集合，通常通过继承 `KeyedCollection<TKey,TItem>`来实现。</span><span class="sxs-lookup"><span data-stu-id="79b32-142">Keyed collections are collections that can be indexed by both an integer and a key and are usually implemented by inheriting from `KeyedCollection<TKey,TItem>`.</span></span>

 <span data-ttu-id="79b32-143">键控集合的内存占用通常较大，并且如果内存开销超过了使用键的益处，则不应使用键控集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-143">Keyed collections usually have larger memory footprints and should not be used if the memory overhead outweighs the benefits of having the keys.</span></span>

 <span data-ttu-id="79b32-144">❌ 不从集合属性或返回集合的方法中返回 null 值。</span><span class="sxs-lookup"><span data-stu-id="79b32-144">❌ DO NOT return null values from collection properties or from methods returning collections.</span></span> <span data-ttu-id="79b32-145">而应返回空集合或空数组。</span><span class="sxs-lookup"><span data-stu-id="79b32-145">Return an empty collection or an empty array instead.</span></span>

 <span data-ttu-id="79b32-146">原则上，应将 null 和空（0 项）集合或数组视为相同。</span><span class="sxs-lookup"><span data-stu-id="79b32-146">The general rule is that null and empty (0 item) collections or arrays should be treated the same.</span></span>

### <a name="snapshots-versus-live-collections"></a><span data-ttu-id="79b32-147">快照集合与实时集合</span><span class="sxs-lookup"><span data-stu-id="79b32-147">Snapshots Versus Live Collections</span></span>
 <span data-ttu-id="79b32-148">表示某个时间点的状态的集合称为快照集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-148">Collections representing a state at some point in time are called snapshot collections.</span></span> <span data-ttu-id="79b32-149">例如，包含从数据库查询返回的行的集合是快照集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-149">For example, a collection containing rows returned from a database query would be a snapshot.</span></span> <span data-ttu-id="79b32-150">始终表示当前状态的集合称为实时集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-150">Collections that always represent the current state are called live collections.</span></span> <span data-ttu-id="79b32-151">例如，`ComboBox` 项的集合为活动集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-151">For example, a collection of `ComboBox` items is a live collection.</span></span>

 <span data-ttu-id="79b32-152">❌ 不从属性返回快照集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-152">❌ DO NOT return snapshot collections from properties.</span></span> <span data-ttu-id="79b32-153">属性应返回实时集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-153">Properties should return live collections.</span></span>

 <span data-ttu-id="79b32-154">属性 getter 应该是非常轻量级的操作。</span><span class="sxs-lookup"><span data-stu-id="79b32-154">Property getters should be very lightweight operations.</span></span> <span data-ttu-id="79b32-155">返回快照需要在 O(n) 操作中创建内部集合的副本。</span><span class="sxs-lookup"><span data-stu-id="79b32-155">Returning a snapshot requires creating a copy of an internal collection in an O(n) operation.</span></span>

 <span data-ttu-id="79b32-156">✔️使用快照集合或实时 `IEnumerable<T>` （或其子类型）来表示可变的集合（即，在未显式修改集合的情况下可以更改）。</span><span class="sxs-lookup"><span data-stu-id="79b32-156">✔️ DO use either a snapshot collection or a live `IEnumerable<T>` (or its subtype) to represent collections that are volatile (i.e., that can change without explicitly modifying the collection).</span></span>

 <span data-ttu-id="79b32-157">一般情况下，表示共享资源（例如，目录中的文件）的所有集合都是易失集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-157">In general, all collections representing a shared resource (e.g., files in a directory) are volatile.</span></span> <span data-ttu-id="79b32-158">此类集合很难或不可能作为实时集合实现，除非该实现只是一个仅正向枚举器。</span><span class="sxs-lookup"><span data-stu-id="79b32-158">Such collections are very difficult or impossible to implement as live collections unless the implementation is simply a forward-only enumerator.</span></span>

## <a name="choosing-between-arrays-and-collections"></a><span data-ttu-id="79b32-159">在数组和集合之间进行选择</span><span class="sxs-lookup"><span data-stu-id="79b32-159">Choosing Between Arrays and Collections</span></span>
 <span data-ttu-id="79b32-160">✔️是否比数组更倾向于集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-160">✔️ DO prefer collections over arrays.</span></span>

 <span data-ttu-id="79b32-161">集合提供了对内容的更多控制，可以随着时间的推移而发展，并且可用性更好。</span><span class="sxs-lookup"><span data-stu-id="79b32-161">Collections provide more control over contents, can evolve over time, and are more usable.</span></span> <span data-ttu-id="79b32-162">此外，不鼓励将数组用于只读场景，因为克隆数组的成本过高。</span><span class="sxs-lookup"><span data-stu-id="79b32-162">In addition, using arrays for read-only scenarios is discouraged because the cost of cloning the array is prohibitive.</span></span> <span data-ttu-id="79b32-163">可用性研究表明，一些开发人员更习惯使用基于集合的 API。</span><span class="sxs-lookup"><span data-stu-id="79b32-163">Usability studies have shown that some developers feel more comfortable using collection-based APIs.</span></span>

 <span data-ttu-id="79b32-164">但是，如果你正在开发低级 API，则对读写场景使用数组可能会更好。</span><span class="sxs-lookup"><span data-stu-id="79b32-164">However, if you are developing low-level APIs, it might be better to use arrays for read-write scenarios.</span></span> <span data-ttu-id="79b32-165">数组的内存占用较小，这有助于减少工作集，并且对数组中元素的访问速度更快，因为它通过运行时进行了优化。</span><span class="sxs-lookup"><span data-stu-id="79b32-165">Arrays have a smaller memory footprint, which helps reduce the working set, and access to elements in an array is faster because it is optimized by the runtime.</span></span>

 <span data-ttu-id="79b32-166">✔️考虑在低级别 Api 中使用数组，以最大程度地减少内存占用和最大化性能。</span><span class="sxs-lookup"><span data-stu-id="79b32-166">✔️ CONSIDER using arrays in low-level APIs to minimize memory consumption and maximize performance.</span></span>

 <span data-ttu-id="79b32-167">✔️使用字节数组而不是字节集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-167">✔️ DO use byte arrays instead of collections of bytes.</span></span>

 <span data-ttu-id="79b32-168">如果属性需要在每次调用属性 getter 时返回新数组（例如，内部数组的副本），则 ❌ 不使用属性的数组。</span><span class="sxs-lookup"><span data-stu-id="79b32-168">❌ DO NOT use arrays for properties if the property would have to return a new array (e.g., a copy of an internal array) every time the property getter is called.</span></span>

## <a name="implementing-custom-collections"></a><span data-ttu-id="79b32-169">实现自定义集合</span><span class="sxs-lookup"><span data-stu-id="79b32-169">Implementing Custom Collections</span></span>
 <span data-ttu-id="79b32-170">✔️考虑在设计新集合时从 `Collection<T>`、`ReadOnlyCollection<T>`或 `KeyedCollection<TKey,TItem>` 继承。</span><span class="sxs-lookup"><span data-stu-id="79b32-170">✔️ CONSIDER inheriting from `Collection<T>`, `ReadOnlyCollection<T>`, or `KeyedCollection<TKey,TItem>` when designing new collections.</span></span>

 <span data-ttu-id="79b32-171">✔️在设计新集合时实现 `IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="79b32-171">✔️ DO implement `IEnumerable<T>` when designing new collections.</span></span> <span data-ttu-id="79b32-172">请考虑实现 `ICollection<T>` 甚至 `IList<T>`。</span><span class="sxs-lookup"><span data-stu-id="79b32-172">Consider implementing `ICollection<T>` or even `IList<T>` where it makes sense.</span></span>

 <span data-ttu-id="79b32-173">实现此类自定义集合时，请遵循 `Collection<T>` 和 `ReadOnlyCollection<T>` 建立的 API 模式。</span><span class="sxs-lookup"><span data-stu-id="79b32-173">When implementing such custom collection, follow the API pattern established by `Collection<T>` and `ReadOnlyCollection<T>` as closely as possible.</span></span> <span data-ttu-id="79b32-174">也就是说，显式实现相同的成员，以及命名参数（与这两个集合命名它们的方式类似）等。</span><span class="sxs-lookup"><span data-stu-id="79b32-174">That is, implement the same members explicitly, name the parameters like these two collections name them, and so on.</span></span>

 <span data-ttu-id="79b32-175">✔️如果集合经常传递到采用这些接口作为输入的 Api，则可考虑实现非泛型集合接口（`IList` 和 `ICollection`）。</span><span class="sxs-lookup"><span data-stu-id="79b32-175">✔️ CONSIDER implementing nongeneric collection interfaces (`IList` and `ICollection`) if the collection will often be passed to APIs taking these interfaces as input.</span></span>

 <span data-ttu-id="79b32-176">❌ 避免使用与集合概念无关的复杂 Api 在类型上实现集合接口。</span><span class="sxs-lookup"><span data-stu-id="79b32-176">❌ AVOID implementing collection interfaces on types with complex APIs unrelated to the concept of a collection.</span></span>

 <span data-ttu-id="79b32-177">❌ 不从非泛型基集合继承，如 `CollectionBase`。</span><span class="sxs-lookup"><span data-stu-id="79b32-177">❌ DO NOT inherit from nongeneric base collections such as `CollectionBase`.</span></span> <span data-ttu-id="79b32-178">改为使用 `Collection<T>`、`ReadOnlyCollection<T>`和 `KeyedCollection<TKey,TItem>`。</span><span class="sxs-lookup"><span data-stu-id="79b32-178">Use `Collection<T>`, `ReadOnlyCollection<T>`, and `KeyedCollection<TKey,TItem>` instead.</span></span>

### <a name="naming-custom-collections"></a><span data-ttu-id="79b32-179">命名自定义集合</span><span class="sxs-lookup"><span data-stu-id="79b32-179">Naming Custom Collections</span></span>
 <span data-ttu-id="79b32-180">创建集合（实现 `IEnumerable`的类型）主要有两个原因：（1）若要创建一个具有特定结构的操作的新数据结构，并且通常与现有数据结构（例如，<xref:System.Collections.Generic.List%601>、<xref:System.Collections.Generic.LinkedList%601>、<xref:System.Collections.Generic.Stack%601>）具有不同的性能特征，请使用（2）创建用于保存一组特定项（例如，<xref:System.Collections.Specialized.StringCollection>）的专用集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-180">Collections (types that implement `IEnumerable`) are created mainly for two reasons: (1) to create a new data structure with structure-specific operations and often different performance characteristics than existing data structures (e.g.,  <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>), and (2) to create a specialized collection for holding a specific set of items (e.g.,  <xref:System.Collections.Specialized.StringCollection>).</span></span> <span data-ttu-id="79b32-181">数据结构最常用于应用程序和库的内部实现。</span><span class="sxs-lookup"><span data-stu-id="79b32-181">Data structures are most often used in the internal implementation of applications and libraries.</span></span> <span data-ttu-id="79b32-182">专用集合主要在 API 中公开（作为属性和参数类型）。</span><span class="sxs-lookup"><span data-stu-id="79b32-182">Specialized collections are mainly to be exposed in APIs (as property and parameter types).</span></span>

 <span data-ttu-id="79b32-183">✔️在实现 `IDictionary` 或 `IDictionary<TKey,TValue>`的抽象名称中使用 "Dictionary" 后缀。</span><span class="sxs-lookup"><span data-stu-id="79b32-183">✔️ DO use the "Dictionary" suffix in names of abstractions implementing `IDictionary` or `IDictionary<TKey,TValue>`.</span></span>

 <span data-ttu-id="79b32-184">✔️在实现 `IEnumerable` 的类型（或其任何子代）的名称中使用 "Collection" 后缀，并表示项列表。</span><span class="sxs-lookup"><span data-stu-id="79b32-184">✔️ DO use the "Collection" suffix in names of types implementing `IEnumerable` (or any of its descendants) and representing a list of items.</span></span>

 <span data-ttu-id="79b32-185">✔️为自定义数据结构使用适当的数据结构名称。</span><span class="sxs-lookup"><span data-stu-id="79b32-185">✔️ DO use the appropriate data structure name for custom data structures.</span></span>

 <span data-ttu-id="79b32-186">❌ 避免使用任何后缀来指定集合抽象名称中的特定实现，如 "LinkedList" 或 "哈希表"。</span><span class="sxs-lookup"><span data-stu-id="79b32-186">❌ AVOID using any suffixes implying particular implementation, such as "LinkedList" or "Hashtable," in names of collection abstractions.</span></span>

 <span data-ttu-id="79b32-187">✔️考虑为集合名称加上项类型的名称。</span><span class="sxs-lookup"><span data-stu-id="79b32-187">✔️ CONSIDER prefixing collection names with the name of the item type.</span></span> <span data-ttu-id="79b32-188">例如，存储类型 `Address` （实现 `IEnumerable<Address>`）的项的集合应命名为 `AddressCollection`。</span><span class="sxs-lookup"><span data-stu-id="79b32-188">For example, a collection storing items of type `Address` (implementing `IEnumerable<Address>`) should be named `AddressCollection`.</span></span> <span data-ttu-id="79b32-189">如果项类型是接口，则可以省略项类型的 “I” 前缀。</span><span class="sxs-lookup"><span data-stu-id="79b32-189">If the item type is an interface, the "I" prefix of the item type can be omitted.</span></span> <span data-ttu-id="79b32-190">因此，可以 `DisposableCollection`调用 <xref:System.IDisposable> 项的集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-190">Thus, a collection of <xref:System.IDisposable> items can be called `DisposableCollection`.</span></span>

 <span data-ttu-id="79b32-191">如果可在框架中添加或已存在相应的可写集合，则✔️考虑在只读集合的名称中使用 "ReadOnly" 前缀。</span><span class="sxs-lookup"><span data-stu-id="79b32-191">✔️ CONSIDER using the "ReadOnly" prefix in names of read-only collections if a corresponding writeable collection might be added or already exists in the framework.</span></span>

 <span data-ttu-id="79b32-192">例如，应 `ReadOnlyStringCollection`调用字符串的只读集合。</span><span class="sxs-lookup"><span data-stu-id="79b32-192">For example, a read-only collection of strings should be called `ReadOnlyStringCollection`.</span></span>

 <span data-ttu-id="79b32-193">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="79b32-193">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="79b32-194">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="79b32-194">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="79b32-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79b32-195">See also</span></span>

- [<span data-ttu-id="79b32-196">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="79b32-196">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="79b32-197">使用准则</span><span class="sxs-lookup"><span data-stu-id="79b32-197">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
