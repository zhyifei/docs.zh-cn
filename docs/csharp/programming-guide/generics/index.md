---
title: 泛型 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: e32eb7c60e01ca72824ffb3a1e1269cf34650f5a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423402"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="20f8a-102">泛型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="20f8a-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="20f8a-103">C# 语言和公共语言运行时 (CLR) 的 2.0 版本中添加了泛型。</span><span class="sxs-lookup"><span data-stu-id="20f8a-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="20f8a-104">泛型将类型参数的概念引入 .NET Framework，这样就可以设计具有以下特征的类和方法：在客户端代码声明并初始化这些类和方法之前，这些类和方法会延迟指定一个或多个类型。</span><span class="sxs-lookup"><span data-stu-id="20f8a-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="20f8a-105">例如，通过使用泛型类型参数 T，可以编写其他客户端代码能够使用的单个类，而不会产生运行时转换或装箱操作的成本或风险，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20f8a-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

<span data-ttu-id="20f8a-106">泛型类和泛型方法兼具可重用性、类型安全性和效率，这是非泛型类和非泛型方法无法实现的。</span><span class="sxs-lookup"><span data-stu-id="20f8a-106">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="20f8a-107">泛型通常与集合以及作用于集合的方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="20f8a-107">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="20f8a-108">.NET Framework 2.0 版类库提供新的命名空间 <xref:System.Collections.Generic>，其中包含几个新的基于泛型的集合类。</span><span class="sxs-lookup"><span data-stu-id="20f8a-108">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="20f8a-109">建议所有定目标到 .NET Framework 2.0 及更高版本的应用程序都使用新增的泛型集合类，而不是旧的非泛型集合类（如 <xref:System.Collections.ArrayList>）。</span><span class="sxs-lookup"><span data-stu-id="20f8a-109">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="20f8a-110">有关详细信息，请参阅 [.NET 中的泛型](../../../standard/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="20f8a-110">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="20f8a-111">当然，也可以创建自定义泛型类型和泛型方法，以提供自己的通用解决方案，设计类型安全的高效模式。</span><span class="sxs-lookup"><span data-stu-id="20f8a-111">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="20f8a-112">以下代码示例演示了出于演示目的的简单泛型链接列表类。</span><span class="sxs-lookup"><span data-stu-id="20f8a-112">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="20f8a-113">（大多数情况下，应使用 .NET Framework 类库提供的 <xref:System.Collections.Generic.List%601> 类，而不是自行创建类。）在通常使用具体类型来指示列表中所存储项的类型的情况下，可使用类型参数 `T`。</span><span class="sxs-lookup"><span data-stu-id="20f8a-113">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="20f8a-114">其使用方法如下：</span><span class="sxs-lookup"><span data-stu-id="20f8a-114">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="20f8a-115">在 `AddHead` 方法中作为方法参数的类型。</span><span class="sxs-lookup"><span data-stu-id="20f8a-115">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="20f8a-116">在 `Node` 嵌套类中作为 `Data` 属性的返回类型。</span><span class="sxs-lookup"><span data-stu-id="20f8a-116">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="20f8a-117">在嵌套类中作为私有成员 `data` 的类型。</span><span class="sxs-lookup"><span data-stu-id="20f8a-117">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="20f8a-118">请注意，T 可用于 `Node` 嵌套类。</span><span class="sxs-lookup"><span data-stu-id="20f8a-118">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="20f8a-119">如果使用具体类型实例化 `GenericList<T>`（例如，作为 `GenericList<int>`），则出现的所有 `T` 都将替换为 `int`。</span><span class="sxs-lookup"><span data-stu-id="20f8a-119">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="20f8a-120">以下代码示例演示了客户端代码如何使用泛型 `GenericList<T>` 类来创建整数列表。</span><span class="sxs-lookup"><span data-stu-id="20f8a-120">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="20f8a-121">只需更改类型参数，即可轻松修改以下代码，创建字符串或任何其他自定义类型的列表：</span><span class="sxs-lookup"><span data-stu-id="20f8a-121">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a><span data-ttu-id="20f8a-122">泛型概述</span><span class="sxs-lookup"><span data-stu-id="20f8a-122">Generics Overview</span></span>  
  
- <span data-ttu-id="20f8a-123">使用泛型类型可以最大限度地重用代码、保护类型安全性以及提高性能。</span><span class="sxs-lookup"><span data-stu-id="20f8a-123">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
- <span data-ttu-id="20f8a-124">泛型最常见的用途是创建集合类。</span><span class="sxs-lookup"><span data-stu-id="20f8a-124">The most common use of generics is to create collection classes.</span></span>  
  
- <span data-ttu-id="20f8a-125">.NET Framework 类库在 <xref:System.Collections.Generic> 命名空间中包含几个新的泛型集合类。</span><span class="sxs-lookup"><span data-stu-id="20f8a-125">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="20f8a-126">应尽可能使用这些类来代替某些类，如 <xref:System.Collections> 命名空间中的 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="20f8a-126">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
- <span data-ttu-id="20f8a-127">可以创建自己的泛型接口、泛型类、泛型方法、泛型事件和泛型委托。</span><span class="sxs-lookup"><span data-stu-id="20f8a-127">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
- <span data-ttu-id="20f8a-128">可以对泛型类进行约束以访问特定数据类型的方法。</span><span class="sxs-lookup"><span data-stu-id="20f8a-128">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
- <span data-ttu-id="20f8a-129">在泛型数据类型中所用类型的信息可在运行时通过使用反射来获取。</span><span class="sxs-lookup"><span data-stu-id="20f8a-129">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20f8a-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="20f8a-130">Related Sections</span></span>  
 <span data-ttu-id="20f8a-131">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="20f8a-131">For more information:</span></span>  
  
- [<span data-ttu-id="20f8a-132">泛型类型参数</span><span class="sxs-lookup"><span data-stu-id="20f8a-132">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [<span data-ttu-id="20f8a-133">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="20f8a-133">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [<span data-ttu-id="20f8a-134">泛型类</span><span class="sxs-lookup"><span data-stu-id="20f8a-134">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [<span data-ttu-id="20f8a-135">泛型接口</span><span class="sxs-lookup"><span data-stu-id="20f8a-135">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [<span data-ttu-id="20f8a-136">泛型方法</span><span class="sxs-lookup"><span data-stu-id="20f8a-136">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [<span data-ttu-id="20f8a-137">泛型委托</span><span class="sxs-lookup"><span data-stu-id="20f8a-137">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [<span data-ttu-id="20f8a-138">C++ 模板和 C# 泛型之间的区别</span><span class="sxs-lookup"><span data-stu-id="20f8a-138">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [<span data-ttu-id="20f8a-139">泛型和反射</span><span class="sxs-lookup"><span data-stu-id="20f8a-139">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [<span data-ttu-id="20f8a-140">运行时中的泛型</span><span class="sxs-lookup"><span data-stu-id="20f8a-140">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="20f8a-141">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="20f8a-141">C# Language Specification</span></span>  
 <span data-ttu-id="20f8a-142">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/types.md#constructed-types)。</span><span class="sxs-lookup"><span data-stu-id="20f8a-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f8a-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="20f8a-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="20f8a-144">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="20f8a-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="20f8a-145">类型</span><span class="sxs-lookup"><span data-stu-id="20f8a-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="20f8a-146">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="20f8a-146">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="20f8a-147">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="20f8a-147">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="20f8a-148">.NET 中的泛型</span><span class="sxs-lookup"><span data-stu-id="20f8a-148">Generics in .NET</span></span>](../../../standard/generics/index.md)
