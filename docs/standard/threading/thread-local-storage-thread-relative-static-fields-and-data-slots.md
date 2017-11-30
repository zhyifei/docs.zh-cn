---
title: "线程本地存储区：线程相关的静态字段和数据槽"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a><span data-ttu-id="ffbae-102">线程本地存储区：线程相关的静态字段和数据槽</span><span class="sxs-lookup"><span data-stu-id="ffbae-102">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>
<span data-ttu-id="ffbae-103">你可以使用托管的线程本地存储 (TLS) 来存储数据的独有线程和应用程序域。</span><span class="sxs-lookup"><span data-stu-id="ffbae-103">You can use managed thread local storage (TLS) to store data that is unique to a thread and application domain.</span></span> <span data-ttu-id="ffbae-104">.NET Framework 提供了两种方式使用托管 TLS： 线程相关的静态字段和数据槽。</span><span class="sxs-lookup"><span data-stu-id="ffbae-104">The .NET Framework provides two ways to use managed TLS: thread-relative static fields and data slots.</span></span>  
  
-   <span data-ttu-id="ffbae-105">使用线程相关的静态字段 (与线程相关`Shared`在 Visual Basic 中的字段) 如果您可以预料到你在编译时的确切需求。</span><span class="sxs-lookup"><span data-stu-id="ffbae-105">Use thread-relative static fields (thread-relative `Shared` fields in Visual Basic) if you can anticipate your exact needs at compile time.</span></span> <span data-ttu-id="ffbae-106">线程相关的静态字段提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="ffbae-106">Thread-relative static fields provide the best performance.</span></span> <span data-ttu-id="ffbae-107">它们还会为你提供编译时类型检查的优点。</span><span class="sxs-lookup"><span data-stu-id="ffbae-107">They also give you the benefits of compile-time type checking.</span></span>  
  
-   <span data-ttu-id="ffbae-108">当你实际要求可能会发现仅在运行时，请使用数据槽。</span><span class="sxs-lookup"><span data-stu-id="ffbae-108">Use data slots when your actual requirements might be discovered only at run time.</span></span> <span data-ttu-id="ffbae-109">数据槽速度较慢且更难以使用比线程相关的静态字段，并且数据存储类型为<xref:System.Object>，因此您必须在使用它之前将它转换为正确的类型。</span><span class="sxs-lookup"><span data-stu-id="ffbae-109">Data slots are slower and more awkward to use than thread-relative static fields, and data is stored as type <xref:System.Object>, so you must cast it to the correct type before you use it.</span></span>  
  
 <span data-ttu-id="ffbae-110">在非托管 c + + 中，你使用`TlsAlloc`来动态分配槽和`__declspec(thread)`来声明，应在线程相关的存储区中分配变量。</span><span class="sxs-lookup"><span data-stu-id="ffbae-110">In unmanaged C++, you use `TlsAlloc` to allocate slots dynamically and `__declspec(thread)` to declare that a variable should be allocated in thread-relative storage.</span></span> <span data-ttu-id="ffbae-111">线程相关的静态字段和数据槽提供此行为的托管的版本。</span><span class="sxs-lookup"><span data-stu-id="ffbae-111">Thread-relative static fields and data slots provide the managed version of this behavior.</span></span>  
  
 <span data-ttu-id="ffbae-112">在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，你可以使用<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>类，以创建第一次使用该对象时延迟初始化的线程本地对象。</span><span class="sxs-lookup"><span data-stu-id="ffbae-112">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to create thread-local objects that are initialized lazily when the object is first consumed.</span></span> <span data-ttu-id="ffbae-113">若要了解详细信息，请参阅[迟缓初始化](../../../docs/framework/performance/lazy-initialization.md)</span><span class="sxs-lookup"><span data-stu-id="ffbae-113">For more information, see [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).</span></span>  
  
## <a name="uniqueness-of-data-in-managed-tls"></a><span data-ttu-id="ffbae-114">托管 TLS 中的数据的唯一性</span><span class="sxs-lookup"><span data-stu-id="ffbae-114">Uniqueness of Data in Managed TLS</span></span>  
 <span data-ttu-id="ffbae-115">无论使用线程相关的静态字段或数据槽的托管 TLS 中的数据是唯一的线程和应用程序域的组合。</span><span class="sxs-lookup"><span data-stu-id="ffbae-115">Whether you use thread-relative static fields or data slots, data in managed TLS is unique to the combination of thread and application domain.</span></span>  
  
-   <span data-ttu-id="ffbae-116">在应用程序域中，一个线程时，无法修改数据从另一个线程，即使这两个线程使用的相同字段或槽。</span><span class="sxs-lookup"><span data-stu-id="ffbae-116">Within an application domain, one thread cannot modify data from another thread, even when both threads use the same field or slot.</span></span>  
  
-   <span data-ttu-id="ffbae-117">当一个线程访问多个应用程序域中的相同字段或槽时，每个应用程序域中保留一个单独的值。</span><span class="sxs-lookup"><span data-stu-id="ffbae-117">When a thread accesses the same field or slot from multiple application domains, a separate value is maintained in each application domain.</span></span>  
  
 <span data-ttu-id="ffbae-118">例如，如果某个线程设置的值与线程相关的静态字段，进入另一个应用程序域，，然后检索字段的值，第二个应用程序域中检索到的值不同于第一个应用程序域中的值。</span><span class="sxs-lookup"><span data-stu-id="ffbae-118">For example, if a thread sets the value of a thread-relative static field, enters another application domain, and then retrieves the value of the field, the value retrieved in the second application domain differs from the value in the first application domain.</span></span> <span data-ttu-id="ffbae-119">在第二个应用程序域中设置字段的新值并不影响第一个应用程序域中的字段的值。</span><span class="sxs-lookup"><span data-stu-id="ffbae-119">Setting a new value for the field in the second application domain does not affect the field's value in the first application domain.</span></span>  
  
 <span data-ttu-id="ffbae-120">同样，当某个线程获取两个不同的应用程序域中的相同命名的数据槽，第一个应用程序域中的数据保留独立的第二个应用程序域中的数据。</span><span class="sxs-lookup"><span data-stu-id="ffbae-120">Similarly, when a thread gets the same named data slot in two different application domains, the data in the first application domain remains independent of the data in the second application domain.</span></span>  
  
## <a name="thread-relative-static-fields"></a><span data-ttu-id="ffbae-121">线程相关的静态字段</span><span class="sxs-lookup"><span data-stu-id="ffbae-121">Thread-Relative Static Fields</span></span>  
 <span data-ttu-id="ffbae-122">如果你知道一段数据始终是唯一的线程和应用程序域组合，应用<xref:System.ThreadStaticAttribute>属性的静态字段。</span><span class="sxs-lookup"><span data-stu-id="ffbae-122">If you know that a piece of data is always unique to a thread and application-domain combination, apply the <xref:System.ThreadStaticAttribute> attribute to the static field.</span></span> <span data-ttu-id="ffbae-123">像使用任何其他静态字段，请使用字段。</span><span class="sxs-lookup"><span data-stu-id="ffbae-123">Use the field as you would use any other static field.</span></span> <span data-ttu-id="ffbae-124">字段中的数据是唯一的使用它的每个线程。</span><span class="sxs-lookup"><span data-stu-id="ffbae-124">The data in the field is unique to each thread that uses it.</span></span>  
  
 <span data-ttu-id="ffbae-125">线程相关的静态字段提供更好的性能比数据槽，并且具有编译时类型检查的好处。</span><span class="sxs-lookup"><span data-stu-id="ffbae-125">Thread-relative static fields provide better performance than data slots and have the benefit of compile-time type checking.</span></span>  
  
 <span data-ttu-id="ffbae-126">请注意类构造函数的任何代码将访问该字段的第一个上下文中的第一个线程上运行。</span><span class="sxs-lookup"><span data-stu-id="ffbae-126">Be aware that any class constructor code will run on the first thread in the first context that accesses the field.</span></span> <span data-ttu-id="ffbae-127">在所有其他线程或上下文相同的应用程序域中，字段将初始化为`null`(`Nothing`在 Visual Basic 中) 如果它们是引用类型，或为其默认值，如果它们是值类型。</span><span class="sxs-lookup"><span data-stu-id="ffbae-127">In all other threads or contexts in the same application domain, the fields will be initialized to `null` (`Nothing` in Visual Basic) if they are reference types, or to their default values if they are value types.</span></span> <span data-ttu-id="ffbae-128">因此，你不应依赖于类的构造函数初始化线程相关的静态字段。</span><span class="sxs-lookup"><span data-stu-id="ffbae-128">Therefore, you should not rely on class constructors to initialize thread-relative static fields.</span></span> <span data-ttu-id="ffbae-129">相反，避免初始化线程相关的静态字段和认为它们将初始化为`null`(`Nothing`) 或为其默认值。</span><span class="sxs-lookup"><span data-stu-id="ffbae-129">Instead, avoid initializing thread-relative static fields and assume that they are initialized to `null` (`Nothing`) or to their default values.</span></span>  
  
## <a name="data-slots"></a><span data-ttu-id="ffbae-130">数据槽</span><span class="sxs-lookup"><span data-stu-id="ffbae-130">Data Slots</span></span>  
 <span data-ttu-id="ffbae-131">.NET Framework 提供了对线程和应用程序域的组合是唯一的动态数据槽。</span><span class="sxs-lookup"><span data-stu-id="ffbae-131">The .NET Framework provides dynamic data slots that are unique to a combination of thread and application-domain.</span></span> <span data-ttu-id="ffbae-132">有两种类型的数据槽： 名为槽和未命名的槽。</span><span class="sxs-lookup"><span data-stu-id="ffbae-132">There are two types of data slots: named slots and unnamed slots.</span></span> <span data-ttu-id="ffbae-133">通过使用实现了同时<xref:System.LocalDataStoreSlot>结构。</span><span class="sxs-lookup"><span data-stu-id="ffbae-133">Both are implemented by using the <xref:System.LocalDataStoreSlot> structure.</span></span>  
  
-   <span data-ttu-id="ffbae-134">若要创建命名的数据槽，请使用<xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType>或<xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="ffbae-134">To create a named data slot, use the <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> or <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ffbae-135">若要获取对现有的已命名的槽的引用，其将名称传递给<xref:System.Threading.Thread.GetNamedDataSlot%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ffbae-135">To get a reference to an existing named slot, pass its name to the <xref:System.Threading.Thread.GetNamedDataSlot%2A> method.</span></span>  
  
-   <span data-ttu-id="ffbae-136">若要创建未命名的数据槽，请使用<xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="ffbae-136">To create an unnamed data slot, use the <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ffbae-137">对于名为和未命名的槽，则使用<xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType>和<xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType>方法用于设置和检索的槽中的信息。</span><span class="sxs-lookup"><span data-stu-id="ffbae-137">For both named and unnamed slots, use the <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> methods to set and retrieve the information in the slot.</span></span> <span data-ttu-id="ffbae-138">这些是始终作用于的线程的当前正在执行它们的数据的静态方法。</span><span class="sxs-lookup"><span data-stu-id="ffbae-138">These are static methods that always act on the data for the thread that is currently executing them.</span></span>  
  
 <span data-ttu-id="ffbae-139">命名的槽可以很方便，因为你可以通过其将名称传递给需要检索槽<xref:System.Threading.Thread.GetNamedDataSlot%2A>方法，而不是维护对未命名的槽的引用。</span><span class="sxs-lookup"><span data-stu-id="ffbae-139">Named slots can be convenient, because you can retrieve the slot when you need it by passing its name to the <xref:System.Threading.Thread.GetNamedDataSlot%2A> method, instead of maintaining a reference to an unnamed slot.</span></span> <span data-ttu-id="ffbae-140">但是，如果另一个组件使用其线程相关的存储区的相同名称和线程执行你的组件和其他组件中的代码，这两个组件可能会破坏彼此的数据。</span><span class="sxs-lookup"><span data-stu-id="ffbae-140">However, if another component uses the same name for its thread-relative storage and a thread executes code from both your component and the other component, the two components might corrupt each other's data.</span></span> <span data-ttu-id="ffbae-141">（此方案假设这两个组件正在运行在相同的应用程序域中，和，它们不设计共享相同的数据）。</span><span class="sxs-lookup"><span data-stu-id="ffbae-141">(This scenario assumes that both components are running in the same application domain, and that they are not designed to share the same data.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbae-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffbae-142">See Also</span></span>  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [<span data-ttu-id="ffbae-143">线程处理</span><span class="sxs-lookup"><span data-stu-id="ffbae-143">Threading</span></span>](../../../docs/standard/threading/index.md)
