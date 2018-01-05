---
title: "在类和结构之间选择"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68a3d2c7335ff15706925f9a7986164e6d9c0c36
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="239ed-102">在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="239ed-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="239ed-103">每个框架设计器将面向的基本设计决策之一是要设计一个类型作为类 （引用类型） 或结构 （值类型）。</span><span class="sxs-lookup"><span data-stu-id="239ed-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="239ed-104">熟悉的引用类型和值类型的行为差异在进行此选择至关重要。</span><span class="sxs-lookup"><span data-stu-id="239ed-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="239ed-105">第一个引用类型和值类型，我们将考虑是引用类型在堆上分配和垃圾回收，而是在堆栈上分配值类型或内联在包含类型，并释放时之间堆栈差异展开或其包含的类型获取释放时。</span><span class="sxs-lookup"><span data-stu-id="239ed-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="239ed-106">因此，分配和释放的值类型是通常价格低于分配和释放的引用类型。</span><span class="sxs-lookup"><span data-stu-id="239ed-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="239ed-107">接下来，引用类型的数组分配行，这意味着的数组元素的堆上驻留的引用类型的实例的只是引用。</span><span class="sxs-lookup"><span data-stu-id="239ed-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="239ed-108">值类型数组分配内联，这意味着数组元素值类型的实际实例。</span><span class="sxs-lookup"><span data-stu-id="239ed-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="239ed-109">因此，分配和释放的值类型数组将更廉价比分配和释放的引用类型数组。</span><span class="sxs-lookup"><span data-stu-id="239ed-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="239ed-110">此外，在大多数情况下值类型数组表现出多更好的引用地址。</span><span class="sxs-lookup"><span data-stu-id="239ed-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="239ed-111">下一个差异与内存使用量。</span><span class="sxs-lookup"><span data-stu-id="239ed-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="239ed-112">值类型获取装箱当强制转换为引用类型或它们实现的接口之一。</span><span class="sxs-lookup"><span data-stu-id="239ed-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="239ed-113">它们获取未装箱当强制转换回值类型。</span><span class="sxs-lookup"><span data-stu-id="239ed-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="239ed-114">因为框是堆上分配和垃圾回收、 过多装箱和取消装箱的对象可以对堆、 垃圾回收器，并最终应用程序的性能有负面影响。</span><span class="sxs-lookup"><span data-stu-id="239ed-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="239ed-115">与此相反，如引用类型强制转换，则会发生没有此类值类型装箱。</span><span class="sxs-lookup"><span data-stu-id="239ed-115">In contrast, no such boxing occurs as reference types are cast.</span></span>  
  
 <span data-ttu-id="239ed-116">接下来，引用类型分配将该引用，而值类型分配复制整个值复制。</span><span class="sxs-lookup"><span data-stu-id="239ed-116">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="239ed-117">因此，大型引用类型的分配的价格低于较大的值类型的分配。</span><span class="sxs-lookup"><span data-stu-id="239ed-117">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="239ed-118">最后，引用类型通过引用进行传递，而通过值传递值类型。</span><span class="sxs-lookup"><span data-stu-id="239ed-118">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="239ed-119">一个引用类型的实例的更改会影响指向实例的所有引用。</span><span class="sxs-lookup"><span data-stu-id="239ed-119">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="239ed-120">将通过值传递它们时复制值类型实例。</span><span class="sxs-lookup"><span data-stu-id="239ed-120">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="239ed-121">当更改值类型的实例时，它是当然的不会影响任何其副本。</span><span class="sxs-lookup"><span data-stu-id="239ed-121">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="239ed-122">由于副本未由用户在显式创建，而隐式创建的自变量传递或返回返回值时，可以更改的值类型可以给许多用户造成混淆。</span><span class="sxs-lookup"><span data-stu-id="239ed-122">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="239ed-123">因此，值类型应是不可变。</span><span class="sxs-lookup"><span data-stu-id="239ed-123">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="239ed-124">作为一条经验法则，大多数框架中的类型应类。</span><span class="sxs-lookup"><span data-stu-id="239ed-124">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="239ed-125">一些，但是，某些情况下在其中的值类型的特征使其更适合使用结构。</span><span class="sxs-lookup"><span data-stu-id="239ed-125">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="239ed-126">**请考虑 ✓**定义而不是类结构，如果该类型的实例很小，通常生存期较短或嵌入其他对象。</span><span class="sxs-lookup"><span data-stu-id="239ed-126">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="239ed-127">**请避免 x**定义一个结构，除非该类型具有所有以下特征：</span><span class="sxs-lookup"><span data-stu-id="239ed-127">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
-   <span data-ttu-id="239ed-128">它逻辑上表示的单个值，类似于基元类型 (`int`，`double`等。)。</span><span class="sxs-lookup"><span data-stu-id="239ed-128">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
-   <span data-ttu-id="239ed-129">它具有实例大小小于 16 字节。</span><span class="sxs-lookup"><span data-stu-id="239ed-129">It has an instance size under 16 bytes.</span></span>  
  
-   <span data-ttu-id="239ed-130">不可变。</span><span class="sxs-lookup"><span data-stu-id="239ed-130">It is immutable.</span></span>  
  
-   <span data-ttu-id="239ed-131">它不需要频繁进行装箱。</span><span class="sxs-lookup"><span data-stu-id="239ed-131">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="239ed-132">在所有其他情况下，应为类定义你的类型。</span><span class="sxs-lookup"><span data-stu-id="239ed-132">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="239ed-133">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="239ed-133">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="239ed-134">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="239ed-134">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239ed-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="239ed-135">See Also</span></span>  
 [<span data-ttu-id="239ed-136">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="239ed-136">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="239ed-137">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="239ed-137">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
