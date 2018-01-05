---
title: "集合准则"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 62205e6bea39214383f6a653d719c0285f374a9f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="guidelines-for-collections"></a><span data-ttu-id="dcb37-102">集合准则</span><span class="sxs-lookup"><span data-stu-id="dcb37-102">Guidelines for Collections</span></span>
<span data-ttu-id="dcb37-103">专门用于操作具有一些公共特征的对象的组的任何类型可被视为集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-103">Any type designed specifically to manipulate a group of objects having some common characteristic can be considered a collection.</span></span> <span data-ttu-id="dcb37-104">它几乎始终适合于要实现此类类型<xref:System.Collections.IEnumerable>或<xref:System.Collections.Generic.IEnumerable%601>，因此在本部分中我们仅考虑实现一个或两个接口要集合的类型。</span><span class="sxs-lookup"><span data-stu-id="dcb37-104">It is almost always appropriate for such types to implement <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601>, so in this section we only consider types implementing one or both of those interfaces to be collections.</span></span>  
  
 <span data-ttu-id="dcb37-105">**X 不**公共 api 使用弱类型的集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-105">**X DO NOT** use weakly typed collections in public APIs.</span></span>  
  
 <span data-ttu-id="dcb37-106">所有返回值和参数表示收集项的类型应为确切的项类型，不是任何 （这仅适用于集合中的公共成员） 及其基类型。</span><span class="sxs-lookup"><span data-stu-id="dcb37-106">The type of all return values and parameters representing collection items should be the exact item type, not any of its base types (this applies only to public members of the collection).</span></span>  
  
 <span data-ttu-id="dcb37-107">**X 不**使用<xref:System.Collections.ArrayList>或<xref:System.Collections.Generic.List%601>公共 Api 中。</span><span class="sxs-lookup"><span data-stu-id="dcb37-107">**X DO NOT** use <xref:System.Collections.ArrayList> or <xref:System.Collections.Generic.List%601> in public APIs.</span></span>  
  
 <span data-ttu-id="dcb37-108">这些类型是用于在内部实现中，不在公共 Api 而设计的数据结构。</span><span class="sxs-lookup"><span data-stu-id="dcb37-108">These types are data structures designed to be used in internal implementation, not in public APIs.</span></span> <span data-ttu-id="dcb37-109">`List<T>`已针对性能和但代价是 cleanness 的 Api 和灵活性的电源优化。</span><span class="sxs-lookup"><span data-stu-id="dcb37-109">`List<T>` is optimized for performance and power at the cost of cleanness of the APIs and flexibility.</span></span> <span data-ttu-id="dcb37-110">例如，如果返回`List<T>`，曾经无法在客户端代码将修改的集合时接收通知。</span><span class="sxs-lookup"><span data-stu-id="dcb37-110">For example, if you return `List<T>`, you will not ever be able to receive notifications when client code modifies the collection.</span></span> <span data-ttu-id="dcb37-111">此外，`List<T>`公开多个成员，如<xref:System.Collections.Generic.List%601.BinarySearch%2A>，，不是有用或适用于许多方案。</span><span class="sxs-lookup"><span data-stu-id="dcb37-111">Also, `List<T>` exposes many members, such as <xref:System.Collections.Generic.List%601.BinarySearch%2A>, that are not useful or applicable in many scenarios.</span></span> <span data-ttu-id="dcb37-112">以下两个部分介绍类型 （抽象） 专为在公共 Api 中使用。</span><span class="sxs-lookup"><span data-stu-id="dcb37-112">The following two sections describe types (abstractions) designed specifically for use in public APIs.</span></span>  
  
 <span data-ttu-id="dcb37-113">**X 不**使用`Hashtable`或`Dictionary<TKey,TValue>`公共 Api 中。</span><span class="sxs-lookup"><span data-stu-id="dcb37-113">**X DO NOT** use `Hashtable` or `Dictionary<TKey,TValue>` in public APIs.</span></span>  
  
 <span data-ttu-id="dcb37-114">这些类型是用于在内部实现中使用的数据结构。</span><span class="sxs-lookup"><span data-stu-id="dcb37-114">These types are data structures designed to be used in internal implementation.</span></span> <span data-ttu-id="dcb37-115">应使用公共 Api <xref:System.Collections.IDictionary>， `IDictionary <TKey, TValue>`，或自定义类型实现一个或两个接口。</span><span class="sxs-lookup"><span data-stu-id="dcb37-115">Public APIs should use <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, or a custom type implementing one or both of the interfaces.</span></span>  
  
 <span data-ttu-id="dcb37-116">**X 不**使用<xref:System.Collections.Generic.IEnumerator%601>， <xref:System.Collections.IEnumerator>，或实现这些接口，任一除用作返回类型的任何其他类型`GetEnumerator`方法。</span><span class="sxs-lookup"><span data-stu-id="dcb37-116">**X DO NOT** use <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, or any other type that implements either of these interfaces, except as the return type of a `GetEnumerator` method.</span></span>  
  
 <span data-ttu-id="dcb37-117">而不从方法返回枚举器的类型`GetEnumerator`不能与使用`foreach`语句。</span><span class="sxs-lookup"><span data-stu-id="dcb37-117">Types returning enumerators from methods other than `GetEnumerator` cannot be used with the `foreach` statement.</span></span>  
  
 <span data-ttu-id="dcb37-118">**X 不**实现`IEnumerator<T>`和`IEnumerable<T>`上相同的类型。</span><span class="sxs-lookup"><span data-stu-id="dcb37-118">**X DO NOT** implement both `IEnumerator<T>` and `IEnumerable<T>` on the same type.</span></span> <span data-ttu-id="dcb37-119">这同样适用于非泛型接口`IEnumerator`和`IEnumerable`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-119">The same applies to the nongeneric interfaces `IEnumerator` and `IEnumerable`.</span></span>  
  
## <a name="collection-parameters"></a><span data-ttu-id="dcb37-120">集合参数</span><span class="sxs-lookup"><span data-stu-id="dcb37-120">Collection Parameters</span></span>  
 <span data-ttu-id="dcb37-121">**✓ 执行**作为参数类型使用的最小专用类型可能。</span><span class="sxs-lookup"><span data-stu-id="dcb37-121">**✓ DO** use the least-specialized type possible as a parameter type.</span></span> <span data-ttu-id="dcb37-122">如何集合，因为参数使用的大多数成员`IEnumerable<T>`接口。</span><span class="sxs-lookup"><span data-stu-id="dcb37-122">Most members taking collections as parameters use the `IEnumerable<T>` interface.</span></span>  
  
 <span data-ttu-id="dcb37-123">**请避免 x**使用<xref:System.Collections.Generic.ICollection%601>或<xref:System.Collections.ICollection>作为参数只是为了访问`Count`属性。</span><span class="sxs-lookup"><span data-stu-id="dcb37-123">**X AVOID** using <xref:System.Collections.Generic.ICollection%601> or <xref:System.Collections.ICollection> as a parameter just to access the `Count` property.</span></span>  
  
 <span data-ttu-id="dcb37-124">相反，请考虑使用`IEnumerable<T>`或`IEnumerable`和动态检查该对象是否实现`ICollection<T>`或`ICollection`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-124">Instead, consider using `IEnumerable<T>` or `IEnumerable` and dynamically checking whether the object implements `ICollection<T>` or `ICollection`.</span></span>  
  
## <a name="collection-properties-and-return-values"></a><span data-ttu-id="dcb37-125">集合属性和返回值</span><span class="sxs-lookup"><span data-stu-id="dcb37-125">Collection Properties and Return Values</span></span>  
 <span data-ttu-id="dcb37-126">**X 不**提供可设置的集合属性。</span><span class="sxs-lookup"><span data-stu-id="dcb37-126">**X DO NOT** provide settable collection properties.</span></span>  
  
 <span data-ttu-id="dcb37-127">用户可以通过先清除该集合，然后添加的新内容替换该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="dcb37-127">Users can replace the contents of the collection by clearing the collection first and then adding the new contents.</span></span> <span data-ttu-id="dcb37-128">如果将替换整个集合作为一种常见情况，请考虑提供`AddRange`对集合的方法。</span><span class="sxs-lookup"><span data-stu-id="dcb37-128">If replacing the whole collection is a common scenario, consider providing the `AddRange` method on the collection.</span></span>  
  
 <span data-ttu-id="dcb37-129">**✓ 执行**使用`Collection<T>`或的子类`Collection<T>`为属性或返回值表示的读/写集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-129">**✓ DO** use `Collection<T>` or a subclass of `Collection<T>` for properties or return values representing read/write collections.</span></span>  
  
 <span data-ttu-id="dcb37-130">如果`Collection<T>`不满足某些要求 (例如，集合必须实现<xref:System.Collections.IList>)，通过实现使用自定义集合`IEnumerable<T>`， `ICollection<T>`，或<xref:System.Collections.Generic.IList%601>。</span><span class="sxs-lookup"><span data-stu-id="dcb37-130">If `Collection<T>` does not meet some requirement (e.g., the collection must not implement <xref:System.Collections.IList>), use a custom collection by implementing `IEnumerable<T>`, `ICollection<T>`, or <xref:System.Collections.Generic.IList%601>.</span></span>  
  
 <span data-ttu-id="dcb37-131">**✓ 执行**使用<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>的一个子类`ReadOnlyCollection<T>`，或在极少数情况下`IEnumerable<T>`为属性或返回值表示的只读集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-131">**✓ DO** use <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, a subclass of `ReadOnlyCollection<T>`, or in rare cases `IEnumerable<T>` for properties or return values representing read-only collections.</span></span>  
  
 <span data-ttu-id="dcb37-132">通常情况下，首选`ReadOnlyCollection<T>`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-132">In general, prefer `ReadOnlyCollection<T>`.</span></span> <span data-ttu-id="dcb37-133">如果不满足某些要求 (例如，集合必须实现`IList`)，通过实现使用自定义集合`IEnumerable<T>`， `ICollection<T>`，或`IList<T>`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-133">If it does not meet some requirement (e.g., the collection must not implement `IList`), use a custom collection by implementing `IEnumerable<T>`, `ICollection<T>`, or `IList<T>`.</span></span> <span data-ttu-id="dcb37-134">如果实现自定义的只读集合，实现`ICollection<T>.ReadOnly`返回 false。</span><span class="sxs-lookup"><span data-stu-id="dcb37-134">If you do implement a custom read-only collection, implement `ICollection<T>.ReadOnly` to return false.</span></span>  
  
 <span data-ttu-id="dcb37-135">在其中您可以确认你将想要支持的唯一情形只进迭代的情况下，你可以只需使用`IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-135">In cases where you are sure that the only scenario you will ever want to support is forward-only iteration, you can simply use `IEnumerable<T>`.</span></span>  
  
 <span data-ttu-id="dcb37-136">**请考虑 ✓**而不直接使用集合使用泛型基集合的子类。</span><span class="sxs-lookup"><span data-stu-id="dcb37-136">**✓ CONSIDER** using subclasses of generic base collections instead of using the collections directly.</span></span>  
  
 <span data-ttu-id="dcb37-137">这允许更好的名称以及添加基集合类型不存在的帮助器成员。</span><span class="sxs-lookup"><span data-stu-id="dcb37-137">This allows for a better name and for adding helper members that are not present on the base collection types.</span></span> <span data-ttu-id="dcb37-138">这是特别适用于高级 Api。</span><span class="sxs-lookup"><span data-stu-id="dcb37-138">This is especially applicable to high-level APIs.</span></span>  
  
 <span data-ttu-id="dcb37-139">**请考虑 ✓**返回的一个子类`Collection<T>`或`ReadOnlyCollection<T>`从非常常用的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="dcb37-139">**✓ CONSIDER** returning a subclass of `Collection<T>` or `ReadOnlyCollection<T>` from very commonly used methods and properties.</span></span>  
  
 <span data-ttu-id="dcb37-140">这将使你可以添加帮助器方法或更改集合实现在将来。</span><span class="sxs-lookup"><span data-stu-id="dcb37-140">This will make it possible for you to add helper methods or change the collection implementation in the future.</span></span>  
  
 <span data-ttu-id="dcb37-141">**请考虑 ✓**使用键控的集合，如果在集合中存储的项具有唯一键 （名称、 Id，等等。）。</span><span class="sxs-lookup"><span data-stu-id="dcb37-141">**✓ CONSIDER** using a keyed collection if the items stored in the collection have unique keys (names, IDs, etc.).</span></span> <span data-ttu-id="dcb37-142">键控的集合是集合可以通过一个整数和一个密钥建立索引并通常实现通过继承`KeyedCollection<TKey,TItem>`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-142">Keyed collections are collections that can be indexed by both an integer and a key and are usually implemented by inheriting from `KeyedCollection<TKey,TItem>`.</span></span>  
  
 <span data-ttu-id="dcb37-143">键控的集合通常更大的内存需求量，并且不能如果内存开销超过了带来密钥的好处。</span><span class="sxs-lookup"><span data-stu-id="dcb37-143">Keyed collections usually have larger memory footprints and should not be used if the memory overhead outweighs the benefits of having the keys.</span></span>  
  
 <span data-ttu-id="dcb37-144">**X 不**返回 null 值，从集合属性或方法返回集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-144">**X DO NOT** return null values from collection properties or from methods returning collections.</span></span> <span data-ttu-id="dcb37-145">而是返回空集合或为空数组。</span><span class="sxs-lookup"><span data-stu-id="dcb37-145">Return an empty collection or an empty array instead.</span></span>  
  
 <span data-ttu-id="dcb37-146">常规规则是，应是 null 和空 （0 项） 集合或数组视为相同。</span><span class="sxs-lookup"><span data-stu-id="dcb37-146">The general rule is that null and empty (0 item) collections or arrays should be treated the same.</span></span>  
  
### <a name="snapshots-versus-live-collections"></a><span data-ttu-id="dcb37-147">与实时集合的快照</span><span class="sxs-lookup"><span data-stu-id="dcb37-147">Snapshots Versus Live Collections</span></span>  
 <span data-ttu-id="dcb37-148">表示时间在某个时间点的状态的集合都称为快照集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-148">Collections representing a state at some point in time are called snapshot collections.</span></span> <span data-ttu-id="dcb37-149">例如，包含从数据库查询返回的行的集合将快照。</span><span class="sxs-lookup"><span data-stu-id="dcb37-149">For example, a collection containing rows returned from a database query would be a snapshot.</span></span> <span data-ttu-id="dcb37-150">始终表示的当前状态的集合都称为实时的集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-150">Collections that always represent the current state are called live collections.</span></span> <span data-ttu-id="dcb37-151">例如，集合`ComboBox`项是实时的集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-151">For example, a collection of `ComboBox` items is a live collection.</span></span>  
  
 <span data-ttu-id="dcb37-152">**X 不**从属性中返回快照集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-152">**X DO NOT** return snapshot collections from properties.</span></span> <span data-ttu-id="dcb37-153">属性应返回实时的集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-153">Properties should return live collections.</span></span>  
  
 <span data-ttu-id="dcb37-154">属性 getter 应非常轻量的操作。</span><span class="sxs-lookup"><span data-stu-id="dcb37-154">Property getters should be very lightweight operations.</span></span> <span data-ttu-id="dcb37-155">返回快照需要 o （n） 操作中创建一份内部集合。</span><span class="sxs-lookup"><span data-stu-id="dcb37-155">Returning a snapshot requires creating a copy of an internal collection in an O(n) operation.</span></span>  
  
 <span data-ttu-id="dcb37-156">**✓ 执行**使用快照集合或实时`IEnumerable<T>`（或其子类型） 来表示是易失性的集合 （即，可以更改而无需显式修改集合）。</span><span class="sxs-lookup"><span data-stu-id="dcb37-156">**✓ DO** use either a snapshot collection or a live `IEnumerable<T>` (or its subtype) to represent collections that are volatile (i.e., that can change without explicitly modifying the collection).</span></span>  
  
 <span data-ttu-id="dcb37-157">一般情况下，所有集合表示共享的资源 （例如，目录中的文件） 都是可变的。</span><span class="sxs-lookup"><span data-stu-id="dcb37-157">In general, all collections representing a shared resource (e.g., files in a directory) are volatile.</span></span> <span data-ttu-id="dcb37-158">此类集合是非常难或无法实现与实时的集合，除非实现是只需一个只进的枚举。</span><span class="sxs-lookup"><span data-stu-id="dcb37-158">Such collections are very difficult or impossible to implement as live collections unless the implementation is simply a forward-only enumerator.</span></span>  
  
## <a name="choosing-between-arrays-and-collections"></a><span data-ttu-id="dcb37-159">数组和集合之间进行选择</span><span class="sxs-lookup"><span data-stu-id="dcb37-159">Choosing Between Arrays and Collections</span></span>  
 <span data-ttu-id="dcb37-160">**✓ 执行**更愿意集合，而数组。</span><span class="sxs-lookup"><span data-stu-id="dcb37-160">**✓ DO** prefer collections over arrays.</span></span>  
  
 <span data-ttu-id="dcb37-161">集合提供更好地控制内容，可以随时间而并且是更易于使用。</span><span class="sxs-lookup"><span data-stu-id="dcb37-161">Collections provide more control over contents, can evolve over time, and are more usable.</span></span> <span data-ttu-id="dcb37-162">此外，在只读方案中使用数组不建议，因为克隆数组的成本很高。</span><span class="sxs-lookup"><span data-stu-id="dcb37-162">In addition, using arrays for read-only scenarios is discouraged because the cost of cloning the array is prohibitive.</span></span> <span data-ttu-id="dcb37-163">可用性研究表明一些开发人员可以更轻松使用基于集合的 Api。</span><span class="sxs-lookup"><span data-stu-id="dcb37-163">Usability studies have shown that some developers feel more comfortable using collection-based APIs.</span></span>  
  
 <span data-ttu-id="dcb37-164">但是，如果你正在开发低级别 Api，它可能是更好的做法用于读写方案的数组。</span><span class="sxs-lookup"><span data-stu-id="dcb37-164">However, if you are developing low-level APIs, it might be better to use arrays for read-write scenarios.</span></span> <span data-ttu-id="dcb37-165">数组具有较小的内存需求量，有助于减少工作集，并对数组中元素的访问速度更快，因为它由运行时优化。</span><span class="sxs-lookup"><span data-stu-id="dcb37-165">Arrays have a smaller memory footprint, which helps reduce the working set, and access to elements in an array is faster because it is optimized by the runtime.</span></span>  
  
 <span data-ttu-id="dcb37-166">**请考虑 ✓**在低级别 Api 中使用数组最大程度减少内存占用和最大程度提高性能。</span><span class="sxs-lookup"><span data-stu-id="dcb37-166">**✓ CONSIDER** using arrays in low-level APIs to minimize memory consumption and maximize performance.</span></span>  
  
 <span data-ttu-id="dcb37-167">**✓ 执行**使用而不是集合的字节的字节数组。</span><span class="sxs-lookup"><span data-stu-id="dcb37-167">**✓ DO** use byte arrays instead of collections of bytes.</span></span>  
  
 <span data-ttu-id="dcb37-168">**X 不**用于属性的数组，如果该属性需要调用属性 getter 每次返回一个新数组 （例如，内部数组的副本）。</span><span class="sxs-lookup"><span data-stu-id="dcb37-168">**X DO NOT** use arrays for properties if the property would have to return a new array (e.g., a copy of an internal array) every time the property getter is called.</span></span>  
  
## <a name="implementing-custom-collections"></a><span data-ttu-id="dcb37-169">实现自定义集合</span><span class="sxs-lookup"><span data-stu-id="dcb37-169">Implementing Custom Collections</span></span>  
 <span data-ttu-id="dcb37-170">**请考虑 ✓**继承自`Collection<T>`， `ReadOnlyCollection<T>`，或`KeyedCollection<TKey,TItem>`设计新的集合时。</span><span class="sxs-lookup"><span data-stu-id="dcb37-170">**✓ CONSIDER** inheriting from `Collection<T>`, `ReadOnlyCollection<T>`, or `KeyedCollection<TKey,TItem>` when designing new collections.</span></span>  
  
 <span data-ttu-id="dcb37-171">**✓ 执行**实现`IEnumerable<T>`设计新的集合时。</span><span class="sxs-lookup"><span data-stu-id="dcb37-171">**✓ DO** implement `IEnumerable<T>` when designing new collections.</span></span> <span data-ttu-id="dcb37-172">请考虑实施`ICollection<T>`甚至`IList<T>`有意义。</span><span class="sxs-lookup"><span data-stu-id="dcb37-172">Consider implementing `ICollection<T>` or even `IList<T>` where it makes sense.</span></span>  
  
 <span data-ttu-id="dcb37-173">在实现此类自定义集合时，遵循由建立 API 模式`Collection<T>`和`ReadOnlyCollection<T>`尽可能。</span><span class="sxs-lookup"><span data-stu-id="dcb37-173">When implementing such custom collection, follow the API pattern established by `Collection<T>` and `ReadOnlyCollection<T>` as closely as possible.</span></span> <span data-ttu-id="dcb37-174">即，显式实现相同的成员，如这些两个集合名称，并因此在 name 参数。</span><span class="sxs-lookup"><span data-stu-id="dcb37-174">That is, implement the same members explicitly, name the parameters like these two collections name them, and so on.</span></span>  
  
 <span data-ttu-id="dcb37-175">**请考虑 ✓**实现非泛型集合接口 (`IList`和`ICollection`) 如果该集合将通常会传递给 Api 采用这些接口作为输入。</span><span class="sxs-lookup"><span data-stu-id="dcb37-175">**✓ CONSIDER** implementing nongeneric collection interfaces (`IList` and `ICollection`) if the collection will often be passed to APIs taking these interfaces as input.</span></span>  
  
 <span data-ttu-id="dcb37-176">**请避免 x**在类型中的集合接口实现的复杂且不与集合中的这一概念相关的 Api。</span><span class="sxs-lookup"><span data-stu-id="dcb37-176">**X AVOID** implementing collection interfaces on types with complex APIs unrelated to the concept of a collection.</span></span>  
  
 <span data-ttu-id="dcb37-177">**X 不**如继承自非泛型基集合`CollectionBase`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-177">**X DO NOT** inherit from nongeneric base collections such as `CollectionBase`.</span></span> <span data-ttu-id="dcb37-178">使用`Collection<T>`， `ReadOnlyCollection<T>`，和`KeyedCollection<TKey,TItem>`相反。</span><span class="sxs-lookup"><span data-stu-id="dcb37-178">Use `Collection<T>`, `ReadOnlyCollection<T>`, and `KeyedCollection<TKey,TItem>` instead.</span></span>  
  
### <a name="naming-custom-collections"></a><span data-ttu-id="dcb37-179">命名自定义集合</span><span class="sxs-lookup"><span data-stu-id="dcb37-179">Naming Custom Collections</span></span>  
 <span data-ttu-id="dcb37-180">集合 (类型实现`IEnumerable`) 创建主要有两个原因: (1) 若要创建新的数据结构与特定于结构的操作，而通常不同的性能特征与现有数据结构 (例如， <xref:System.Collections.Generic.List%601>，<xref:System.Collections.Generic.LinkedList%601>， <xref:System.Collections.Generic.Stack%601>)，和 (2) 若要创建专用的集合用于保存一组特定的项 (例如， <xref:System.Collections.Specialized.StringCollection>)。</span><span class="sxs-lookup"><span data-stu-id="dcb37-180">Collections (types that implement `IEnumerable`) are created mainly for two reasons: (1) to create a new data structure with structure-specific operations and often different performance characteristics than existing data structures (e.g.,  <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>), and (2) to create a specialized collection for holding a specific set of items (e.g.,  <xref:System.Collections.Specialized.StringCollection>).</span></span> <span data-ttu-id="dcb37-181">数据结构最常用于应用程序和库的内部实现。</span><span class="sxs-lookup"><span data-stu-id="dcb37-181">Data structures are most often used in the internal implementation of applications and libraries.</span></span> <span data-ttu-id="dcb37-182">专用的集合是主要是为了在 （作为属性和参数类型） 的 Api 中公开。</span><span class="sxs-lookup"><span data-stu-id="dcb37-182">Specialized collections are mainly to be exposed in APIs (as property and parameter types).</span></span>  
  
 <span data-ttu-id="dcb37-183">**✓ 执行**实现的抽象名称中使用"字典"后缀`IDictionary`或`IDictionary<TKey,TValue>`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-183">**✓ DO** use the "Dictionary" suffix in names of abstractions implementing `IDictionary` or `IDictionary<TKey,TValue>`.</span></span>  
  
 <span data-ttu-id="dcb37-184">**✓ 执行**在实现的类型的名称中使用"集合"后缀`IEnumerable`（或其任意后代） 和表示的项的列表。</span><span class="sxs-lookup"><span data-stu-id="dcb37-184">**✓ DO** use the "Collection" suffix in names of types implementing `IEnumerable` (or any of its descendants) and representing a list of items.</span></span>  
  
 <span data-ttu-id="dcb37-185">**✓ 执行**使用自定义数据结构的适当的数据结构名称。</span><span class="sxs-lookup"><span data-stu-id="dcb37-185">**✓ DO** use the appropriate data structure name for custom data structures.</span></span>  
  
 <span data-ttu-id="dcb37-186">**请避免 x**的集合的抽象的名称中使用并暗示特定实现，如"LinkedList"或"哈希表，"任何后缀。</span><span class="sxs-lookup"><span data-stu-id="dcb37-186">**X AVOID** using any suffixes implying particular implementation, such as "LinkedList" or "Hashtable," in names of collection abstractions.</span></span>  
  
 <span data-ttu-id="dcb37-187">**请考虑 ✓**前缀同名的项类型的集合名称。</span><span class="sxs-lookup"><span data-stu-id="dcb37-187">**✓ CONSIDER** prefixing collection names with the name of the item type.</span></span> <span data-ttu-id="dcb37-188">例如，存储类型的项集合`Address`(实现`IEnumerable<Address>`) 应该被命名为`AddressCollection`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-188">For example, a collection storing items of type `Address` (implementing `IEnumerable<Address>`) should be named `AddressCollection`.</span></span> <span data-ttu-id="dcb37-189">如果项的类型是接口，"I"前缀的项类型，则可以省略。</span><span class="sxs-lookup"><span data-stu-id="dcb37-189">If the item type is an interface, the "I" prefix of the item type can be omitted.</span></span> <span data-ttu-id="dcb37-190">因此，集合<xref:System.IDisposable>可调用项`DisposableCollection`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-190">Thus, a collection of <xref:System.IDisposable> items can be called `DisposableCollection`.</span></span>  
  
 <span data-ttu-id="dcb37-191">**请考虑 ✓**如果相应的可写集合可能添加或已存在 framework 中的只读集合的名称中使用"ReadOnly"前缀。</span><span class="sxs-lookup"><span data-stu-id="dcb37-191">**✓ CONSIDER** using the "ReadOnly" prefix in names of read-only collections if a corresponding writeable collection might be added or already exists in the framework.</span></span>  
  
 <span data-ttu-id="dcb37-192">例如，应调用字符串的只读集合`ReadOnlyStringCollection`。</span><span class="sxs-lookup"><span data-stu-id="dcb37-192">For example, a read-only collection of strings should be called `ReadOnlyStringCollection`.</span></span>  
  
 <span data-ttu-id="dcb37-193">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="dcb37-193">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dcb37-194">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="dcb37-194">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb37-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcb37-195">See Also</span></span>  
 [<span data-ttu-id="dcb37-196">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="dcb37-196">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="dcb37-197">使用准则</span><span class="sxs-lookup"><span data-stu-id="dcb37-197">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
