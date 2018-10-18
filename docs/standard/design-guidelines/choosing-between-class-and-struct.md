---
title: 在类和结构之间选择
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06661cb2c34d1da9085fa2129cb0c3307b99097e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865548"
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="903c3-102">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="903c3-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="903c3-103">每个框架设计者面临的基本设计决策之一是将类型设计为类（引用类型）还是结构（值类型）。</span><span class="sxs-lookup"><span data-stu-id="903c3-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="903c3-104">要做出合适的选择，深入理解引用类型和值类型的行为差异非常重要。</span><span class="sxs-lookup"><span data-stu-id="903c3-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="903c3-105">第一个差别引用类型和值类型，我们将考虑是引用类型是在堆上分配和垃圾回收，而是在堆栈上分配值类型或包含中的以内联方式类型，并且已解除分配时堆栈展开时或当其包含类型会被解除分配。</span><span class="sxs-lookup"><span data-stu-id="903c3-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="903c3-106">因此，分配和释放的值类型是通常比分配和释放的引用类型成本更低。</span><span class="sxs-lookup"><span data-stu-id="903c3-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="903c3-107">接下来，引用类型的数组分配行，这意味着元素的数组只是对驻留在堆上的引用类型的实例。</span><span class="sxs-lookup"><span data-stu-id="903c3-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="903c3-108">值类型数组分配内联，这意味着数组元素值类型的实际实例。</span><span class="sxs-lookup"><span data-stu-id="903c3-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="903c3-109">因此，分配和释放的值类型数组将比分配和释放的引用类型数组更便宜。</span><span class="sxs-lookup"><span data-stu-id="903c3-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="903c3-110">此外，在大多数情况下值类型数组表现出多更好的引用地址。</span><span class="sxs-lookup"><span data-stu-id="903c3-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="903c3-111">下一个差异与内存使用量。</span><span class="sxs-lookup"><span data-stu-id="903c3-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="903c3-112">获取装箱值类型，当强制转换为引用类型或它们实现的接口之一。</span><span class="sxs-lookup"><span data-stu-id="903c3-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="903c3-113">他们会收到未装箱时强制转换回值类型。</span><span class="sxs-lookup"><span data-stu-id="903c3-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="903c3-114">因为框是在堆上分配和垃圾回收、 过多装箱和取消装箱的对象可以对堆、 垃圾回收器，并最终应用程序性能的负面影响。</span><span class="sxs-lookup"><span data-stu-id="903c3-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="903c3-115">与此相反，没有此类值类型装箱会出现引用类型转换。</span><span class="sxs-lookup"><span data-stu-id="903c3-115">In contrast, no such boxing occurs as reference types are cast.</span></span>  
  
 <span data-ttu-id="903c3-116">接下来，引用类型分配将引用，而值类型分配复制的整个值复制。</span><span class="sxs-lookup"><span data-stu-id="903c3-116">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="903c3-117">因此，大型的引用类型的分配是大值类型的分配比更便宜。</span><span class="sxs-lookup"><span data-stu-id="903c3-117">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="903c3-118">最后，引用类型是通过引用传递，而按值传递值类型。</span><span class="sxs-lookup"><span data-stu-id="903c3-118">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="903c3-119">引用类型的实例的更改会影响所有指向实例的引用。</span><span class="sxs-lookup"><span data-stu-id="903c3-119">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="903c3-120">按值传递值类型实例进行复制。</span><span class="sxs-lookup"><span data-stu-id="903c3-120">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="903c3-121">当更改值类型的实例时，它当然不会影响任何其副本。</span><span class="sxs-lookup"><span data-stu-id="903c3-121">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="903c3-122">因为副本不由用户显式创建，但会隐式创建参数传递或返回值返回时，可以更改的值类型可以是给许多用户造成混淆。</span><span class="sxs-lookup"><span data-stu-id="903c3-122">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="903c3-123">因此，值类型应为不可变。</span><span class="sxs-lookup"><span data-stu-id="903c3-123">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="903c3-124">根据经验，大部分的框架中的类型应为类。</span><span class="sxs-lookup"><span data-stu-id="903c3-124">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="903c3-125">有，但是，某些情况下，在其中一个值类型的特性使其更适合使用结构。</span><span class="sxs-lookup"><span data-stu-id="903c3-125">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="903c3-126">**✓ CONSIDER** 定义而不是类结构，如果该类型的实例很小，通常生存期较短或嵌入其他对象。</span><span class="sxs-lookup"><span data-stu-id="903c3-126">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="903c3-127">**X AVOID** 定义一个结构，除非该类型具有所有以下特征：</span><span class="sxs-lookup"><span data-stu-id="903c3-127">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
-   <span data-ttu-id="903c3-128">它逻辑上表示的单个值，类似于基元类型 (`int`， `double`，等等。)。</span><span class="sxs-lookup"><span data-stu-id="903c3-128">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
-   <span data-ttu-id="903c3-129">它的实例大小小于 16 字节。</span><span class="sxs-lookup"><span data-stu-id="903c3-129">It has an instance size under 16 bytes.</span></span>  
  
-   <span data-ttu-id="903c3-130">它是不可变。</span><span class="sxs-lookup"><span data-stu-id="903c3-130">It is immutable.</span></span>  
  
-   <span data-ttu-id="903c3-131">它不会频繁装箱。</span><span class="sxs-lookup"><span data-stu-id="903c3-131">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="903c3-132">在所有其他情况下，应将您的类型定义为类。</span><span class="sxs-lookup"><span data-stu-id="903c3-132">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="903c3-133">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="903c3-133">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="903c3-134">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="903c3-134">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903c3-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="903c3-135">See also</span></span>

- [<span data-ttu-id="903c3-136">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="903c3-136">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="903c3-137">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="903c3-137">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
