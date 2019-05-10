---
title: 在类和结构之间选择
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
author: KrzysztofCwalina
ms.openlocfilehash: 5041368ca1a440698c399c935ac72aba2002c3ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615265"
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="92915-102">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="92915-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="92915-103">每个框架设计者面临的基本设计决策之一是将类型设计为类（引用类型）还是结构（值类型）。</span><span class="sxs-lookup"><span data-stu-id="92915-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="92915-104">要做出合适的选择，深入理解引用类型和值类型的行为差异非常重要。</span><span class="sxs-lookup"><span data-stu-id="92915-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="92915-105">我们要考虑的第一个引用类型和值类型之间的区别是引用类型在堆上分配并进行垃圾回收，而值类型在堆栈中分配并在堆栈展开时被释放，或内联包含类型并在它们的包含类型被释放时被释放。</span><span class="sxs-lookup"><span data-stu-id="92915-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="92915-106">因此，值类型的分配和释放通常比引用类型的分配和释放开销更低。</span><span class="sxs-lookup"><span data-stu-id="92915-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="92915-107">其次，引用类型数组是乱序分配的，这意味着数组元素只是对驻留在堆上的引用类型的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="92915-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="92915-108">值类型数组是内联分配的，这意味着数组元素是值类型的实际实例。</span><span class="sxs-lookup"><span data-stu-id="92915-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="92915-109">因此，值类型数组的分配和释放比引用类型数组的分配和释放开销更低。</span><span class="sxs-lookup"><span data-stu-id="92915-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="92915-110">此外，在大多数情况下，值类型数组具有更好的引用地址。</span><span class="sxs-lookup"><span data-stu-id="92915-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="92915-111">下一个区别与内存使用有关。</span><span class="sxs-lookup"><span data-stu-id="92915-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="92915-112">当值类型转换为引用类型或它们实现的接口之一时，该值类型会被装箱。</span><span class="sxs-lookup"><span data-stu-id="92915-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="92915-113">它们在转回值类型时会被拆箱。</span><span class="sxs-lookup"><span data-stu-id="92915-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="92915-114">因为箱是在堆上分配的对象并会被垃圾回收，所以过多的装箱和拆箱会对堆、垃圾回收器以及最终应用程序的性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="92915-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="92915-115">相反，在转换引用类型时不会发生这样的装箱。</span><span class="sxs-lookup"><span data-stu-id="92915-115">In contrast, no such boxing occurs as reference types are cast.</span></span> <span data-ttu-id="92915-116">（有关详细信息，请参阅[装箱和取消装箱](../../csharp/programming-guide/types/boxing-and-unboxing.md)）。</span><span class="sxs-lookup"><span data-stu-id="92915-116">(For more information, see [Boxing and Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).</span></span>
  
 <span data-ttu-id="92915-117">再次，引用类型的赋值复制引用，而值类型的赋值复制整个值。</span><span class="sxs-lookup"><span data-stu-id="92915-117">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="92915-118">因此，大型引用类型的赋值比大型值类型的赋值开销更低。</span><span class="sxs-lookup"><span data-stu-id="92915-118">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="92915-119">最后，引用类型通过引用传递，而值类型通过值传递。</span><span class="sxs-lookup"><span data-stu-id="92915-119">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="92915-120">对引用类型实例的更改会影响指向该实例的所有引用。</span><span class="sxs-lookup"><span data-stu-id="92915-120">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="92915-121">值类型实例在按值传递时被复制。</span><span class="sxs-lookup"><span data-stu-id="92915-121">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="92915-122">当更改值类型的实例时，它当然不会影响其任何副本。</span><span class="sxs-lookup"><span data-stu-id="92915-122">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="92915-123">由于副本并非由用户显式创建，而是在传递参数或返回返回值时隐式创建，因此可以更改的值类型可能会让许多用户感到困惑。</span><span class="sxs-lookup"><span data-stu-id="92915-123">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="92915-124">所以，值类型应不可变。</span><span class="sxs-lookup"><span data-stu-id="92915-124">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="92915-125">一般来说，框架中的大多数类型应该是类。</span><span class="sxs-lookup"><span data-stu-id="92915-125">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="92915-126">但是，在某些情况下，值类型的特征使得其更适合使用结构。</span><span class="sxs-lookup"><span data-stu-id="92915-126">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="92915-127">**✓ 考虑**如果类型的实例比较小并且通常生存期较短或者通常嵌入在其他对象中，则定义结构而不是类。</span><span class="sxs-lookup"><span data-stu-id="92915-127">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="92915-128">**X 避免**定义一个结构，除非该类型具有所有以下特征：</span><span class="sxs-lookup"><span data-stu-id="92915-128">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
- <span data-ttu-id="92915-129">它逻辑上表示单个值，类似于基元类型（`int`， `double`，等等）。</span><span class="sxs-lookup"><span data-stu-id="92915-129">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
- <span data-ttu-id="92915-130">它的实例大小小于 16 字节。</span><span class="sxs-lookup"><span data-stu-id="92915-130">It has an instance size under 16 bytes.</span></span>  
  
- <span data-ttu-id="92915-131">它是不可变的。</span><span class="sxs-lookup"><span data-stu-id="92915-131">It is immutable.</span></span>  
  
- <span data-ttu-id="92915-132">它不会频繁装箱。</span><span class="sxs-lookup"><span data-stu-id="92915-132">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="92915-133">在所有其他情况下，应将类型定义为类。</span><span class="sxs-lookup"><span data-stu-id="92915-133">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="92915-134">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="92915-134">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="92915-135">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="92915-135">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92915-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="92915-136">See also</span></span>

- [<span data-ttu-id="92915-137">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="92915-137">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="92915-138">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="92915-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
