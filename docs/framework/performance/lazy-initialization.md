---
title: "延迟初始化 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET 中的延迟初始化, 介绍"
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# 延迟初始化
一个对象的延迟初始化意味着该对象的创建将会延迟至第一次使用该对象时。（在本主题中，术语“延迟初始化”和“延迟实例化”是同义词。）延迟初始化主要用于提高性能，避免浪费计算，并减少程序内存要求。  以下是最常见的方案：  
  
-   有一个对象的创建开销很大，而程序可能不会使用它。  例如，假定您在内存中有一个 `Customer` 对象，该对象的 `Orders` 属性包含一个很大的 `Order` 对象数组，该数组需要数据库连接以进行初始化。  如果用户从未要求显示 Orders 或在计算中使用其数据，则没有理由使用系统内存或计算周期来创建它。  通过使用 `Lazy<Orders>` 将 `Orders` 对象声明为延迟初始化，可以避免在不使用该对象的情况下浪费系统资源。  
  
-   有一个对象的创建开销很大，您想要将创建它的时间延迟到完成其他开销大的操作之后。  例如，假定您的程序在启动时加载若干个对象实例，但只有一些对象实例需要立即执行。  通过将不必要的对象的初始化延迟到已创建必要的对象之后，可以提高程序的启动性能。  
  
 尽管您可以编写自己的代码来执行延迟初始化，但我们推荐使用 <xref:System.Lazy%601>。  <xref:System.Lazy%601> 及其相关的类型还支持线程安全，并提供一致的异常传播策略。  
  
 下表列出了 .NET Framework 版本 4 提供的、可在不同方案中启用延迟初始化的类型。  
  
|类型|说明|  
|--------|--------|  
|<xref:System.Lazy%601>|一个包装类，可为任意类库或用户定义的类型提供延迟初始化语义。|  
|<xref:System.Threading.ThreadLocal%601>|类似于 <xref:System.Lazy%601>，只不过它基于本地线程提供延迟初始化语义。  每个线程都可以访问自己的唯一值。|  
|<xref:System.Threading.LazyInitializer>|为对象的延迟初始化提供高级的 `static`（Visual Basic 中为 `Shared`）方法，此方法不需要类开销。|  
  
## 基本的延迟初始化  
 若要定义延迟初始化的类型（例如，`MyType`），请使用 `Lazy<MyType>`（Visual Basic 中为 `Lazy(Of MyType)`），如以下示例中所示。  如果在 <xref:System.Lazy%601> 构造函数中没有传递委托，则在第一次访问值属性时，将通过使用 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> 来创建包装类型。  如果该类型没有默认的构造函数，则引发运行时异常。  
  
 在以下示例中，假定 `Orders` 是一个类，该类包含从数据库检索的 `Order` 对象的数组。  `Customer` 对象包含一个 `Orders` 实例，但根据用户操作，可能不需要来自 `Orders` 对象的数据。  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 此外，还可以在 <xref:System.Lazy%601> 构造函数中传递一个委托，用于在创建时调用包装类的特定构造函数重载，并执行所需的任何其他初始化步骤，如以下示例中所示。  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 在创建延迟对象之后，在第一次访问延迟变量的 <xref:System.Lazy%601.Value%2A> 属性之前，将不会创建 `Orders` 的实例。  在第一次访问包装类型时，将会创建并返回该包装类型，并将其存储起来以备任何将来的访问。  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 <xref:System.Lazy%601> 对象始终返回初始化时使用的相同对象或值。  因此，<xref:System.Lazy%601.Value%2A> 属性是只读的。  如果 <xref:System.Lazy%601.Value%2A> 存储引用类型，则不能为它分配新对象。（但是，可以更改其可设置的公共字段和属性的值。）如果 <xref:System.Lazy%601.Value%2A> 存储一个值类型，则不能修改它的值。  但是，可以使用新的参数通过再次调用变量构造函数来创建新的变量。  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 在第一次访问 <xref:System.Lazy%601.Value%2A> 属性之前，新的延迟实例（与早期的延迟实例类似）不会实例化 `Orders`。  
  
### 线程安全初始化  
 默认情况下，<xref:System.Lazy%601> 对象是线程安全的。  这意味着如果构造函数未指定线程安全性的类型，它创建的 <xref:System.Lazy%601> 对象都是线程安全的。  在多线程方案中，要访问线程安全的 <xref:System.Lazy%601> 对象的 <xref:System.Lazy%601.Value%2A> 属性的第一个线程将为所有线程上的所有后续访问初始化该对象，并且所有线程都共享相同数据。  因此，由哪个线程初始化对象并不重要，争用条件将是良性的。  
  
> [!NOTE]
>  您可以使用异常缓存将此一致性扩展至错误条件。  有关更多信息，请参见下部分，[延迟对象中的异常](../../../docs/framework/performance/lazy-initialization.md#ExceptionsInLazyObjects)。  
  
 下面的示例演示了同一个 `Lazy<int>` 实例对于三个不同的线程具有相同的值。  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 如果在每个线程上需要不同的数据，请使用 <xref:System.Threading.ThreadLocal%601> 类型，如本主题后面所述。  
  
 一些 <xref:System.Lazy%601> 构造函数具有一个名为 `isThreadSafe` 的布尔参数，该参数用于指定是否将从多个线程访问 <xref:System.Lazy%601.Value%2A> 属性。  如果您打算只从一个线程访问该属性，请传入 `false` 以获得适度的性能好处。  如果您打算从多个线程访问该属性，请传入 `true` 以指示 <xref:System.Lazy%601> 实例正确处理争用条件（在此条件下，一个线程将在初始化时引发一个异常）。  
  
 一些 <xref:System.Lazy%601> 构造函数具有一个名为 `mode` 的 <xref:System.Threading.LazyThreadSafetyMode> 参数。  这些构造函数提供一个额外的线程安全性模式。  下表显示指定线程安全性的构造函数参数如何影响 <xref:System.Lazy%601> 对象的线程安全性。  每个构造函数最多具有一个这样的参数：  
  
|对象的线程安全性|`LazyThreadSafetyMode` `mode` 参数|布尔 `isThreadSafe` 参数|无线程安全性参数|  
|--------------|--------------------------------------|--------------------------|--------------|  
|线程完全安全；一次只有一个线程尝试初始化值。|<xref:System.Threading.LazyThreadSafetyMode>|`true`|可以。|  
|线程不安全。|<xref:System.Threading.LazyThreadSafetyMode>|`false`|不适用。|  
|线程完全安全；线程通过争用来初始化值。|<xref:System.Threading.LazyThreadSafetyMode>|不适用。|不适用。|  
  
 如该表所示，为 `mode` 参数指定 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 与为 `isThreadSafe` 参数指定 `true` 相同，指定 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 与指定 `false` 相同。  
  
 指定 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 允许多个线程尝试初始化 <xref:System.Lazy%601> 实例。  只有一个线程在争用中胜出，所有其他线程将接收由胜出线程初始化的值。  如果在初始化期间线程引发异常，则该线程不接收由胜出线程设置的值。  因为不缓存异常，因此访问 <xref:System.Lazy%601.Value%2A> 属性的后续尝试可能导致成功的初始化。  这与在其他模式中处理异常的方式不同，后者将在下一节中进行说明。  有关更多信息，请参见 <xref:System.Threading.LazyThreadSafetyMode> 枚举。  
  
<a name="ExceptionsInLazyObjects"></a>   
## 延迟对象中的异常  
 如上文所述，<xref:System.Lazy%601> 对象始终返回在初始化时使用的相同对象或值，因此，<xref:System.Lazy%601.Value%2A> 属性是只读的。  如果您启用异常缓存，则此永久性还将扩展至异常行为。  如果某个迟缓初始化的对象启用了异常缓存，并在首次访问 <xref:System.Lazy%601.Value%2A> 属性时从其初始化方法引发异常，则以后每次尝试访问 <xref:System.Lazy%601.Value%2A> 属性时都会引发相同的异常。  换句话说，决不会重新调用包装类型的构造函数，即使在多线程方案中也是如此。  因此，<xref:System.Lazy%601> 对象不能对一次访问引发异常，而对后续的访问返回值。  
  
 当您使用任何采用初始化方法（`valueFactory` 参数）的 <xref:System.Lazy%601?displayProperty=fullName> 构造函数时，会启用异常缓存；例如，当您使用 `Lazy(T)(Func(T))` 构造函数时，会启用异常缓存。  如果构造函数还采用 <xref:System.Threading.LazyThreadSafetyMode> 值（`mode` 参数），请指定 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 或 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>。  指定初始化方法会为这两种模式启用异常缓存。  初始化方法可以非常简单。  例如，它可以调用 `T` 的默认构造函数：`new Lazy<Contents>(() => new Contents(), mode)` \(C\#\) 或 `New Lazy(Of Contents)(Function() New Contents())` \(Visual Basic\)。  如果您使用不指定初始化方法的 <xref:System.Lazy%601?displayProperty=fullName> 构造函数，则不会缓存 `T` 默认构造函数引发的异常。  有关更多信息，请参见 <xref:System.Threading.LazyThreadSafetyMode>。  
  
> [!NOTE]
>  如果您创建了 <xref:System.Lazy%601> 对象，并将其 `isThreadSafe` 构造函数参数设置为 `false` 或将 `mode` 构造函数参数设置为 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>，则必须从单个线程访问 <xref:System.Lazy%601> 对象或提供您自己的同步。  这适用于对象的所有方面，包括异常缓存。  
  
 如上一节所述，通过指定 <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> 创建的 <xref:System.Lazy%601> 对象处理异常的方式不同。  使用 <xref:System.Threading.LazyThreadSafetyMode>，多个线程可以通过争用来初始化 <xref:System.Lazy%601> 实例。  在这种情况下，不缓存异常，访问 <xref:System.Lazy%601.Value%2A> 属性的尝试可以继续下去，直到初始化成功。  
  
 下表总结了 <xref:System.Lazy%601> 构造函数控制异常缓存的方式。  
  
|构造函数|线程安全模式|使用初始化方法|缓存异常|  
|----------|------------|-------------|----------|  
|Lazy\(T\)\(\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|否|否|  
|Lazy\(T\)\(Func\(T\)\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|是|是|  
|Lazy\(T\)\(Boolean\)|`True` \(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) 或 `false` \(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|否|否|  
|Lazy\(T\)\(Func\(T\), Boolean\)|`True` \(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) 或 `false` \(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|是|是|  
|Lazy\(T\)\(LazyThreadSafetyMode\)|用户指定|否|否|  
|Lazy\(T\)\(Func\(T\), LazyThreadSafetyMode\)|用户指定|是|如果用户指定 <xref:> System.Threading.LazyThreadSafetyMode.PublicationOnly?qualifyHint=False&autoUpgrade=True 则为“否”，否则为“是”。|  
  
## 实现延迟初始化属性  
 若要通过使用延迟初始化来实现一个公共属性，请将该属性的支持字段定义为 <xref:System.Lazy%601>，并从该属性的 `get` 访问器中返回 <xref:System.Lazy%601.Value%2A> 属性。  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 <xref:System.Lazy%601.Value%2A> 属性是只读的；因此，公开它的属性不具有 `set` 访问器。  如果需要 <xref:System.Lazy%601> 对象支持的读\/写属性，则 `set` 访问器必须创建新的 <xref:System.Lazy%601> 对象并将它分配给支持存储区。  `set` 访问器必须创建返回传给 `set` 访问器的新属性值的 lambda 表达式，并将该表达式传给新 <xref:System.Lazy%601> 对象的构造函数。  下一次访问 <xref:System.Lazy%601.Value%2A> 属性将导致初始化新的 <xref:System.Lazy%601>，其 <xref:System.Lazy%601.Value%2A> 属性此后将返回分配给该属性的新值。  进行这种复杂的安排是为了保持内置到 <xref:System.Lazy%601> 的多线程保护。  否则，属性访问器必须缓存 <xref:System.Lazy%601.Value%2A> 属性返回的第一个值并只修改缓存的值，您必须编写自己的线程安全代码来完成此工作。  由于 <xref:System.Lazy%601> 对象支持的读\/写属性需要更多初始化，性能可能变低。  此外，根据特定的方案，可能需要更大的协调量来避免 setter 和 getter 之间的争用条件。  
  
## 线程本地延迟初始化  
 在某些多线程方案中，可能要为每个线程提供它自己的私有数据。  此类数据称为“线程本地数据”。  在 .NET Framework 3.5 和更低版本中，可以将 `ThreadStatic` 特性应用于静态变量以使其成为线程本地变量。  但是，使用 `ThreadStatic` 特性会导致细小的错误。  例如，即使基本的初始化语句也将导致该变量只在访问它的第一个线程上进行初始化，如以下示例中所示。  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 在所有其他线程上，该变量将通过使用默认值（零）来进行初始化。  在 .NET Framework 4 中，作为一种替代方法，可以使用 <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> 类型创建基于实例的线程本地变量，此变量可通过您提供的 <xref:System.Action%601> 委托在所有线程上进行初始化。  在以下示例中，所有访问 `counter` 的线程都会将其起始值看作 1。  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601> 包装其对象与 <xref:System.Lazy%601> 非常相似，但存在以下主要差别：  
  
-   通过使用不可从其他线程访问的线程自己的私有数据，每个线程都可初始化线程本地变量。  
  
-   <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=fullName> 属性是可读写的，可进行任意次数的修改。  这会影响异常传播，例如，一个 `get` 操作可能会引发一个异常，但下一个操作可能会成功地初始化该值。  
  
-   如果未提供初始化委托，则 <xref:System.Threading.ThreadLocal%601> 将通过使用其包装类型的默认值对其进行初始化。  就这一点而言，<xref:System.Threading.ThreadLocal%601> 与 <xref:System.ThreadStaticAttribute> 特性是一致的。  
  
 下面的示例演示了访问 `ThreadLocal<int>` 实例的每个线程如何获取自己的唯一的数据副本。  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## Parallel.For 和 ForEach 中的线程本地变量  
 当使用 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 方法或 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 方法以并行方式循环访问数据源时，可以使用具有对线程本地数据的内置支持的重载。  在这些方法中，可通过使用本地委托来创建、访问和清理数据来实现线程本地化。  有关更多信息，请参见[How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)和[How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md)。  
  
## 对低开销方案使用延迟初始化  
 在必须延迟初始化大量对象的方案中，您可能会认为在 <xref:System.Lazy%601> 中包装每个对象需要过多的内存或过多的计算资源。  或者，您可能对如何公开延迟初始化有严格的要求。  在这种情况下，可以使用 <xref:System.Threading.LazyInitializer?displayProperty=fullName> 类的 `static`（在 Visual Basic 中为 `Shared`）方法来延迟初始化每个对象，并且不将这些对象包装在 <xref:System.Lazy%601> 实例中。  
  
 在以下示例中，假定不将整个 `Orders` 对象包装在一个 <xref:System.Lazy%601> 对象中，而是在需要的时候延迟初始化单个 `Order` 对象。  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 在此示例中，请注意，在循环的每次迭代中都会调用初始化过程。  在多线程方案中，要调用初始化过程的第一个线程的值将可以由所有线程看到。  后面的线程还将调用初始化过程，但不使用它们的结果。  如果这种潜在的争用条件是不可接受的，请使用采用一个布尔参数和一个同步对象的 <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=fullName> 重载。  
  
## 请参阅  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [如何：执行对象的延迟初始化](../../../docs/framework/performance/how-to-perform-lazy-initialization-of-objects.md)