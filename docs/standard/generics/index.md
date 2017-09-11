---
title: ".NET Framework 中的泛型 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generic methods, type inference
- generics [.NET Framework], collections
- generic interfaces [.NET Framework]
- constructed generic types
- nested generic types
- generic type definitions
- generic classes [.NET Framework]
- generics [.NET Framework], interfaces
- generics [.NET Framework], about
- generics [.NET Framework]
- generic collections [.NET Framework]
- generic delegates [.NET Framework]
- generic type arguments
- generics [.NET Framework], delegates
- generics [.NET Framework], features
- constraints [.NET Framework]
- generic types
- generic type parameters
ms.assetid: 2994d786-c5c7-4666-ab23-4c83129fe39c
caps.latest.revision: 23
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9e352489bb22b691d9024a651f3864d2604a90cd
ms.contentlocale: zh-cn
ms.lasthandoff: 05/02/2017

---
# <a name="generics-in-the-net-framework"></a><span data-ttu-id="6fbb7-102">.NET Framework 中的泛型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-102">Generics in the .NET Framework</span></span>
<span data-ttu-id="6fbb7-103"><a name="top"></a>借助泛型，可以根据要处理的精确数据类型定制方法、类、结构或接口。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-103"><a name="top"></a> Generics let you tailor a method, class, structure, or interface to the precise data type it acts upon.</span></span> <span data-ttu-id="6fbb7-104">例如，可以使用 <xref:System.Collections.Generic.Dictionary%602> 泛型类并指定允许的键和值类型，而不使用允许键和值为任意类型的 <xref:System.Collections.Hashtable> 类。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-104">For example, instead of using the <xref:System.Collections.Hashtable> class, which allows keys and values to be of any type, you can use the <xref:System.Collections.Generic.Dictionary%602> generic class and specify the type allowed for the key and the type allowed for the value.</span></span> <span data-ttu-id="6fbb7-105">泛型的优点包括：代码的可重用性增加，类型安全性提高。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-105">Among the benefits of generics are increased code reusability and type safety.</span></span>  
  
 <span data-ttu-id="6fbb7-106">本主题提供对 .NET Framework 中泛型的概述以及泛型类型和方法的摘要。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-106">This topic provides an overview of generics in the .NET Framework and a summary of generic types or methods.</span></span> <span data-ttu-id="6fbb7-107">它包含下列部分：</span><span class="sxs-lookup"><span data-stu-id="6fbb7-107">It contains the following sections:</span></span>  
  
-   [<span data-ttu-id="6fbb7-108">定义和使用泛型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-108">Defining and Using Generics</span></span>](#defining_and_using_generics)  
  
-   [<span data-ttu-id="6fbb7-109">泛型术语</span><span class="sxs-lookup"><span data-stu-id="6fbb7-109">Generics Terminology</span></span>](#generics_terminology)  
  
-   [<span data-ttu-id="6fbb7-110">类库和语言支持</span><span class="sxs-lookup"><span data-stu-id="6fbb7-110">Class Library and Language Support</span></span>](#class_library_and_language_support)  
  
-   [<span data-ttu-id="6fbb7-111">嵌套类型和泛型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-111">Nested Types and Generics</span></span>](#nested_types_and_generics)  
  
-   [<span data-ttu-id="6fbb7-112">相关主题</span><span class="sxs-lookup"><span data-stu-id="6fbb7-112">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="6fbb7-113">参考</span><span class="sxs-lookup"><span data-stu-id="6fbb7-113">Reference</span></span>](#reference)  
  
<a name="defining_and_using_generics"></a>   
## <a name="defining-and-using-generics"></a><span data-ttu-id="6fbb7-114">定义和使用泛型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-114">Defining and Using Generics</span></span>  
 <span data-ttu-id="6fbb7-115">泛型是为所存储或使用的一个或多个类型具有占位符（类型形参）的类、结构、接口和方法。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-115">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span> <span data-ttu-id="6fbb7-116">泛型集合类可以将类型形参用作其存储的对象类型的占位符；类型形参呈现为其字段的类型和其方法的参数类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-116">A generic collection class might use a type parameter as a placeholder for the type of objects that it stores; the type parameters appear as the types of its fields and the parameter types of its methods.</span></span> <span data-ttu-id="6fbb7-117">泛型方法可将其类型形参用作其返回值的类型或用作其形参之一的类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-117">A generic method might use its type parameter as the type of its return value or as the type of one of its formal parameters.</span></span> <span data-ttu-id="6fbb7-118">以下代码举例说明了一个简单的泛型类定义。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-118">The following code illustrates a simple generic class definition.</span></span>  
  
 <span data-ttu-id="6fbb7-119">[!code-cpp[Conceptual.Generics.Overview#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#2)]
 [!code-csharp[Conceptual.Generics.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#2)]
 [!code-vb[Conceptual.Generics.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="6fbb7-119">[!code-cpp[Conceptual.Generics.Overview#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#2)]
 [!code-csharp[Conceptual.Generics.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#2)]
 [!code-vb[Conceptual.Generics.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#2)]</span></span>  
  
 <span data-ttu-id="6fbb7-120">创建泛型类的实例时，指定用于替代类型形参的实际类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-120">When you create an instance of a generic class, you specify the actual types to substitute for the type parameters.</span></span> <span data-ttu-id="6fbb7-121">在类型形参出现的每一处位置用选定的类型进行替代，这会建立一个被称为构造泛型类的新泛型类。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-121">This establishes a new generic class, referred to as a constructed generic class, with your chosen types substituted everywhere that the type parameters appear.</span></span> <span data-ttu-id="6fbb7-122">你将得到根据你选择的类型而定制的类型安全类，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-122">The result is a type-safe class that is tailored to your choice of types, as the following code illustrates.</span></span>  
  
 <span data-ttu-id="6fbb7-123">[!code-cpp[Conceptual.Generics.Overview#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#3)]
 [!code-csharp[Conceptual.Generics.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#3)]
 [!code-vb[Conceptual.Generics.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="6fbb7-123">[!code-cpp[Conceptual.Generics.Overview#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#3)]
 [!code-csharp[Conceptual.Generics.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#3)]
 [!code-vb[Conceptual.Generics.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#3)]</span></span>  
  
<a name="generics_terminology"></a>   
### <a name="generics-terminology"></a><span data-ttu-id="6fbb7-124">泛型术语</span><span class="sxs-lookup"><span data-stu-id="6fbb7-124">Generics terminology</span></span>  
 <span data-ttu-id="6fbb7-125">以下术语用于讨论 NET Framework 中的泛型：</span><span class="sxs-lookup"><span data-stu-id="6fbb7-125">The following terms are used to discuss generics in the .NET Framework:</span></span>  
  
-   <span data-ttu-id="6fbb7-126">*泛型类型定义*是用作模板的类、结构或接口声明，带有可包含或使用的类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-126">A *generic type definition* is a class, structure, or interface declaration that functions as a template, with placeholders for the types that it can contain or use.</span></span> <span data-ttu-id="6fbb7-127">例如，<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 类可以包含两种类型，即键和值。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-127">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class can contain two types: keys and values.</span></span> <span data-ttu-id="6fbb7-128">由于泛型类型定义只是一个模板，所以你无法创建作为泛型类型定义的类、结构或接口的实例。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-128">Because a generic type definition is only a template, you cannot create instances of a class, structure, or interface that is a generic type definition.</span></span>  
  
-   <span data-ttu-id="6fbb7-129">*泛型类型参数*（或*类型参数*）是泛型类型或方法定义中的占位符。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-129">*Generic type parameters*, or *type parameters*, are the placeholders in a generic type or method definition.</span></span> <span data-ttu-id="6fbb7-130"><xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 泛型类型包含两个类型参数，即 `TKey` 和 `TValue`，它们分别表示键和值的类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-130">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> generic type has two type parameters, `TKey` and `TValue`, that represent the types of its keys and values.</span></span>  
  
-   <span data-ttu-id="6fbb7-131">*构造泛型类型*（或*构造类型*）是为泛型类型定义的泛型类型参数指定类型所生成的结果。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-131">A *constructed generic type*, or *constructed type*, is the result of specifying types for the generic type parameters of a generic type definition.</span></span>  
  
-   <span data-ttu-id="6fbb7-132">*泛型类型自变量*是用于代替泛型类型参数的任意类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-132">A *generic type argument* is any type that is substituted for a generic type parameter.</span></span>  
  
-   <span data-ttu-id="6fbb7-133">常见术语*泛型类型*包括构造类型和泛型类型定义。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-133">The general term *generic type* includes both constructed types and generic type definitions.</span></span>  
  
-   <span data-ttu-id="6fbb7-134">借助泛型类型参数的*协变*和*逆变*，可以使用类型自变量的派生程度比目标构造类型更高（协变）或更低（逆变）的构造泛型类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-134">*Covariance* and *contravariance* of generic type parameters enable you to use constructed generic types whose type arguments are more derived (covariance) or less derived (contravariance) than a target constructed type.</span></span> <span data-ttu-id="6fbb7-135">协变和逆变统称为“变体”。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-135">Covariance and contravariance are collectively referred to as *variance*.</span></span> <span data-ttu-id="6fbb7-136">有关详细信息，请参阅[协变和逆变](../../../docs/standard/generics/covariance-and-contravariance.md)。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-136">For more information, see [Covariance and Contravariance](../../../docs/standard/generics/covariance-and-contravariance.md).</span></span>  
  
-   <span data-ttu-id="6fbb7-137">*约束*是对泛型类型参数的限制。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-137">*Constraints* are limits placed on generic type parameters.</span></span> <span data-ttu-id="6fbb7-138">例如，为了确保能够对类型实例进行排序，可以将类型参数限制为仅供实现 <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> 泛型接口的类型使用。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-138">For example, you might limit a type parameter to types that implement the <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> generic interface, to ensure that instances of the type can be ordered.</span></span> <span data-ttu-id="6fbb7-139">此外，你还可以将类型形参限制为具有特定基类、具有默认构造函数或作为引用类型或值类型的类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-139">You can also constrain type parameters to types that have a particular base class, that have a default constructor, or that are reference types or value types.</span></span> <span data-ttu-id="6fbb7-140">泛型类型的用户不能替换不满足约束条件的类型实参。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-140">Users of the generic type cannot substitute type arguments that do not satisfy the constraints.</span></span>  
  
-   <span data-ttu-id="6fbb7-141">*泛型方法定义*是包含以下两个参数列表的方法：泛型类型参数列表和形参列表。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-141">A *generic method definition* is a method with two parameter lists: a list of generic type parameters and a list of formal parameters.</span></span> <span data-ttu-id="6fbb7-142">类型形参可作为返回类型或形参类型出现，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-142">Type parameters can appear as the return type or as the types of the formal parameters, as the following code shows.</span></span>  
  
 <span data-ttu-id="6fbb7-143">[!code-cpp[Conceptual.Generics.Overview#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#4)]
 [!code-csharp[Conceptual.Generics.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#4)]
 [!code-vb[Conceptual.Generics.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="6fbb7-143">[!code-cpp[Conceptual.Generics.Overview#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Generics.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#4)]
[!code-vb[Conceptual.Generics.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#4)]</span></span>  
  
 <span data-ttu-id="6fbb7-144">泛型方法可出现在泛型或非泛型类型中。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-144">Generic methods can appear on generic or nongeneric types.</span></span> <span data-ttu-id="6fbb7-145">值得注意的是，方法不会仅因为它属于泛型类型或甚至因为它有类型为封闭类型泛型参数的形参而成为泛型方法。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-145">It is important to note that a method is not generic just because it belongs to a generic type, or even because it has formal parameters whose types are the generic parameters of the enclosing type.</span></span> <span data-ttu-id="6fbb7-146">只有当方法有属于自己的类型形参列表时才是泛型方法。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-146">A method is generic only if it has its own list of type parameters.</span></span> <span data-ttu-id="6fbb7-147">在以下代码中，只有方法 `G` 是泛型方法。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-147">In the following code, only method `G` is generic.</span></span>  
  
 <span data-ttu-id="6fbb7-148">[!code-cpp[Conceptual.Generics.Overview#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#5)]
 [!code-csharp[Conceptual.Generics.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#5)]
 [!code-vb[Conceptual.Generics.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="6fbb7-148">[!code-cpp[Conceptual.Generics.Overview#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Generics.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#5)]
[!code-vb[Conceptual.Generics.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#5)]</span></span>  
  
 [<span data-ttu-id="6fbb7-149">返回页首</span><span class="sxs-lookup"><span data-stu-id="6fbb7-149">Back to top</span></span>](#top)  
  
<a name="advantages_limitations"></a>   
## <a name="advantages-and-disadvantages-of-generics"></a><span data-ttu-id="6fbb7-150">泛型的利与弊</span><span class="sxs-lookup"><span data-stu-id="6fbb7-150">Advantages and disadvantages of generics</span></span>  
 <span data-ttu-id="6fbb7-151">使用泛型集合和委托有很多好处：</span><span class="sxs-lookup"><span data-stu-id="6fbb7-151">There are many advantages to using generic collections and delegates:</span></span>  
  
-   <span data-ttu-id="6fbb7-152">类型安全。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-152">Type safety.</span></span> <span data-ttu-id="6fbb7-153">泛型将类型安全的负担从你那里转移到编译器。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-153">Generics shift the burden of type safety from you to the compiler.</span></span> <span data-ttu-id="6fbb7-154">没有必要编写代码来测试正确的数据类型，因为它会在编译时强制执行。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-154">There is no need to write code to test for the correct data type because it is enforced at compile time.</span></span> <span data-ttu-id="6fbb7-155">降低了强制类型转换的必要性和运行时错误的可能性。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-155">The need for type casting and the possibility of run-time errors are reduced.</span></span>  
  
-   <span data-ttu-id="6fbb7-156">代码更少且可以更轻松地重用代码。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-156">Less code and code is more easily reused.</span></span> <span data-ttu-id="6fbb7-157">无需从基类型继承，无需重写成员。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-157">There is no need to inherit from a base type and override members.</span></span> <span data-ttu-id="6fbb7-158">例如，<xref:System.Collections.Generic.LinkedList%601> 可供立即使用。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-158">For example, the <xref:System.Collections.Generic.LinkedList%601> is ready for immediate use.</span></span> <span data-ttu-id="6fbb7-159">例如，你可以使用下列变量声明来创建字符串的链接列表：</span><span class="sxs-lookup"><span data-stu-id="6fbb7-159">For example, you can create a linked list of strings with the following variable declaration:</span></span>  
  
     <span data-ttu-id="6fbb7-160">[!code-cpp[HowToGeneric#24](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/source2.cpp#24)]
     [!code-csharp[HowToGeneric#24](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/source2.cs#24)]
     [!code-vb[HowToGeneric#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/source2.vb#24)]</span><span class="sxs-lookup"><span data-stu-id="6fbb7-160">[!code-cpp[HowToGeneric#24](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/source2.cpp#24)]
 [!code-csharp[HowToGeneric#24](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/source2.cs#24)]
 [!code-vb[HowToGeneric#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/source2.vb#24)]</span></span>  
  
-   <span data-ttu-id="6fbb7-161">性能更好。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-161">Better performance.</span></span> <span data-ttu-id="6fbb7-162">泛型集合类型通常能更好地存储和操作值类型，因为无需对值类型进行装箱。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-162">Generic collection types generally perform better for storing and manipulating value types because there is no need to box the value types.</span></span>  
  
-   <span data-ttu-id="6fbb7-163">泛型委托可以在无需创建多个委托类的情况下进行类型安全的回调。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-163">Generic delegates enable type-safe callbacks without the need to create multiple delegate classes.</span></span> <span data-ttu-id="6fbb7-164">例如，使用 <xref:System.Predicate%601> 泛型委托，可以创建方法来实现自己的特定类型搜索条件，并将自己的方法与 <xref:System.Array> 类型的方法（如 <xref:System.Array.Find%2A>、<xref:System.Array.FindLast%2A> 和 <xref:System.Array.FindAll%2A>）结合使用。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-164">For example, the <xref:System.Predicate%601> generic delegate allows you to create a method that implements your own search criteria for a particular type and to use your method with methods of the <xref:System.Array> type such as <xref:System.Array.Find%2A>, <xref:System.Array.FindLast%2A>, and <xref:System.Array.FindAll%2A>.</span></span>  
  
-   <span data-ttu-id="6fbb7-165">泛型简化动态生成的代码。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-165">Generics streamline dynamically generated code.</span></span> <span data-ttu-id="6fbb7-166">使用具有动态生成的代码的泛型时，无需生成类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-166">When you use generics with dynamically generated code you do not need to generate the type.</span></span> <span data-ttu-id="6fbb7-167">这会增加方案数量，在这些方案中你可以使用轻量动态方法而非生成整个程序集。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-167">This increases the number of scenarios in which you can use lightweight dynamic methods instead of generating entire assemblies.</span></span> <span data-ttu-id="6fbb7-168">有关详细信息，请参阅“如何：定义和执行动态方法和 DynamicMethod。”</span><span class="sxs-lookup"><span data-stu-id="6fbb7-168">For more information, see How to: Define and Execute Dynamic Methods and DynamicMethod.</span></span>  
  
 <span data-ttu-id="6fbb7-169">以下是泛型的一些局限：</span><span class="sxs-lookup"><span data-stu-id="6fbb7-169">The following are some limitations of generics:</span></span>  
  
-   <span data-ttu-id="6fbb7-170">泛型类型可以派生自大部分的基类，如 <xref:System.MarshalByRefObject>（约束可用于要求泛型类型参数派生自 <xref:System.MarshalByRefObject> 等基类）。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-170">Generic types can be derived from most base classes, such as <xref:System.MarshalByRefObject> (and constraints can be used to require that generic type parameters derive from base classes like <xref:System.MarshalByRefObject>).</span></span> <span data-ttu-id="6fbb7-171">不过，[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 不支持上下文绑定泛型类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-171">However, the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support context-bound generic types.</span></span> <span data-ttu-id="6fbb7-172">泛型类型可以派生自 <xref:System.ContextBoundObject>，但尝试创建相应类型的实例会导致 <xref:System.TypeLoadException> 抛出。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-172">A generic type can be derived from <xref:System.ContextBoundObject>, but trying to create an instance of that type causes a <xref:System.TypeLoadException>.</span></span>  
  
-   <span data-ttu-id="6fbb7-173">枚举不能具有泛型类型形参。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-173">Enumerations cannot have generic type parameters.</span></span> <span data-ttu-id="6fbb7-174">枚举偶尔可为泛型（例如，因为它嵌套在被定义使用 Visual Basic、C# 或 C++ 的泛型类型中）。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-174">An enumeration can be generic only incidentally (for example, because it is nested in a generic type that is defined using Visual Basic, C#, or C++).</span></span> <span data-ttu-id="6fbb7-175">有关详细信息，请参阅[通用类型系统](../../../docs/standard/base-types/common-type-system.md)中的“枚举”。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-175">For more information, see "Enumerations" in [Common Type System](../../../docs/standard/base-types/common-type-system.md).</span></span>  
  
-   <span data-ttu-id="6fbb7-176">轻量动态方法不能是泛型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-176">Lightweight dynamic methods cannot be generic.</span></span>  
  
-   <span data-ttu-id="6fbb7-177">在 Visual Basic、C# 和 C++ 中，包含在泛型类型中的嵌套类型不能被实例化，除非已将类型分配给所有封闭类型的类型形参。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-177">In Visual Basic, C#, and C++, a nested type that is enclosed in a generic type cannot be instantiated unless types have been assigned to the type parameters of all enclosing types.</span></span> <span data-ttu-id="6fbb7-178">另一种说法是：在反射中，定义使用这些语言的嵌套类型包括其所有封闭类型的类型形参。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-178">Another way of saying this is that in reflection, a nested type that is defined using these languages includes the type parameters of all its enclosing types.</span></span> <span data-ttu-id="6fbb7-179">这使封闭类型的类型形参可在嵌套类型的成员定义中使用。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-179">This allows the type parameters of enclosing types to be used in the member definitions of a nested type.</span></span> <span data-ttu-id="6fbb7-180">有关详细信息，请参阅 <xref:System.Type.MakeGenericType%2A> 中的“嵌套类型”。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-180">For more information, see "Nested Types" in <xref:System.Type.MakeGenericType%2A>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fbb7-181">通过在动态程序集中触发代码或通过使用 [Ilasm.exe (IL Assembler)](../../../docs/framework/tools/ilasm-exe-il-assembler.md) 定义的嵌套类型不需要包括其封闭类型的类型参数；然而，如果不包括，类型参数就不会在嵌套类的范围内。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-181">A nested type that is defined by emitting code in a dynamic assembly or by using the [Ilasm.exe (IL Assembler)](../../../docs/framework/tools/ilasm-exe-il-assembler.md) is not required to include the type parameters of its enclosing types; however, if it does not include them, the type parameters are not in scope in the nested class.</span></span>  
  
     <span data-ttu-id="6fbb7-182">有关详细信息，请参阅 <xref:System.Type.MakeGenericType%2A> 中的“嵌套类型”。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-182">For more information, see "Nested Types" in <xref:System.Type.MakeGenericType%2A>.</span></span>  
  
 [<span data-ttu-id="6fbb7-183">返回页首</span><span class="sxs-lookup"><span data-stu-id="6fbb7-183">Back to top</span></span>](#top)  
  
<a name="class_library_and_language_support"></a>   
## <a name="class-library-and-language-support"></a><span data-ttu-id="6fbb7-184">类库和语言支持</span><span class="sxs-lookup"><span data-stu-id="6fbb7-184">Class Library and Language Support</span></span>  
 <span data-ttu-id="6fbb7-185">.NET Framework 提供了许多以下命名空间中的泛型集合类：</span><span class="sxs-lookup"><span data-stu-id="6fbb7-185">The .NET Framework provides a number of generic collection classes in the following namespaces:</span></span>  
  
-   <span data-ttu-id="6fbb7-186"><xref:System.Collections.Generic> 命名空间编录了 .NET Framework 提供的大部分泛型集合类型，如 <xref:System.Collections.Generic.List%601> 和 <xref:System.Collections.Generic.Dictionary%602> 泛型类。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-186">The <xref:System.Collections.Generic> namespace catalogs most of the generic collection types provided by the .NET Framework, such as the <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602> generic classes.</span></span>  
  
-   <span data-ttu-id="6fbb7-187"><xref:System.Collections.ObjectModel> 命名空间编录了其他用于向类用户公开对象模型的泛型集合类型，如 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 泛型类。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-187">The <xref:System.Collections.ObjectModel> namespace catalogs additional generic collection types, such as the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> generic class, that are useful for exposing object models to users of your classes.</span></span>  
  
 <span data-ttu-id="6fbb7-188"><xref:System> 命名空间提供用于实现排序和相等比较的泛型接口，以及事件处理程序、转换和搜索谓词的泛型委托类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-188">Generic interfaces for implementing sort and equality comparisons are provided in the <xref:System> namespace, along with generic delegate types for event handlers, conversions, and search predicates.</span></span>  
  
 <span data-ttu-id="6fbb7-189"><xref:System.Reflection> 命名空间现已开始支持泛型以检查泛型类型和泛型方法；<xref:System.Reflection.Emit> 现已开始支持泛型以触发包含泛型类型和方法的动态程序集；<xref:System.CodeDom> 现已开始支持泛型以生成包括泛型的源图。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-189">Support for generics has been added to the <xref:System.Reflection> namespace for examining generic types and generic methods, to <xref:System.Reflection.Emit> for emitting dynamic assemblies that contain generic types and methods, and to <xref:System.CodeDom> for generating source graphs that include generics.</span></span>  
  
 <span data-ttu-id="6fbb7-190">为了支持在 Microsoft 中间语言 (MSIL) 内使用泛型类型，公共语言运行时提供了新的操作码和前缀，包括 <xref:System.Reflection.Emit.OpCodes.Stelem>、<xref:System.Reflection.Emit.OpCodes.Ldelem>、<xref:System.Reflection.Emit.OpCodes.Unbox_Any>、<xref:System.Reflection.Emit.OpCodes.Constrained> 和 <xref:System.Reflection.Emit.OpCodes.Readonly>。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-190">The common language runtime provides new opcodes and prefixes to support generic types in Microsoft intermediate language (MSIL), including <xref:System.Reflection.Emit.OpCodes.Stelem>, <xref:System.Reflection.Emit.OpCodes.Ldelem>, <xref:System.Reflection.Emit.OpCodes.Unbox_Any>, <xref:System.Reflection.Emit.OpCodes.Constrained>, and <xref:System.Reflection.Emit.OpCodes.Readonly>.</span></span>  
  
 <span data-ttu-id="6fbb7-191">Visual C++、C# 和 Visual Basic 都对定义和使用泛型提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-191">Visual C++, C#, and Visual Basic all provide full support for defining and using generics.</span></span> <span data-ttu-id="6fbb7-192">有关语言支持的详细信息，请参阅 [Visual Basic 中的泛型类型](~/docs/visual-basic/programming-guide/language-features/data-types/generic-types.md)、[泛型简介](~/docs/csharp/programming-guide/generics/introduction-to-generics.md)和 [Visual C++ 中的泛型概述](http://msdn.microsoft.com/library/21f10637-0fce-4916-b925-6c86a126d3aa)。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-192">For more information about language support, see [Generic Types in Visual Basic](~/docs/visual-basic/programming-guide/language-features/data-types/generic-types.md), [Introduction to Generics](~/docs/csharp/programming-guide/generics/introduction-to-generics.md), and [Overview of Generics in Visual C++](http://msdn.microsoft.com/library/21f10637-0fce-4916-b925-6c86a126d3aa).</span></span>  
  
 [<span data-ttu-id="6fbb7-193">返回页首</span><span class="sxs-lookup"><span data-stu-id="6fbb7-193">Back to top</span></span>](#top)  
  
<a name="nested_types_and_generics"></a>   
## <a name="nested-types-and-generics"></a><span data-ttu-id="6fbb7-194">嵌套类型和泛型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-194">Nested Types and Generics</span></span>  
 <span data-ttu-id="6fbb7-195">嵌套在泛型类型中的类型可取决于封闭泛型类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-195">A type that is nested in a generic type can depend on the type parameters of the enclosing generic type.</span></span> <span data-ttu-id="6fbb7-196">公共语言运行时将嵌套类型看作泛型，即使它们不具有自己的泛型类型形参。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-196">The common language runtime considers nested types to be generic, even if they do not have generic type parameters of their own.</span></span> <span data-ttu-id="6fbb7-197">创建嵌套类型的实例时，必须指定所有封闭泛型类型的类型实参。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-197">When you create an instance of a nested type, you must specify type arguments for all enclosing generic types.</span></span>  
  
 [<span data-ttu-id="6fbb7-198">返回页首</span><span class="sxs-lookup"><span data-stu-id="6fbb7-198">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="6fbb7-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="6fbb7-199">Related Topics</span></span>  
  
|<span data-ttu-id="6fbb7-200">标题</span><span class="sxs-lookup"><span data-stu-id="6fbb7-200">Title</span></span>|<span data-ttu-id="6fbb7-201">说明</span><span class="sxs-lookup"><span data-stu-id="6fbb7-201">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6fbb7-202">.NET Framework 中的泛型集合</span><span class="sxs-lookup"><span data-stu-id="6fbb7-202">Generic Collections in the .NET Framework</span></span>](../../../docs/standard/generics/collections.md)|<span data-ttu-id="6fbb7-203">描述 .NET Framework 中的泛型集合类和其他泛型类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-203">Describes generic collection classes and other generic types in the .NET Framework.</span></span>|  
|[<span data-ttu-id="6fbb7-204">用于控制数组和列表的泛型委托</span><span class="sxs-lookup"><span data-stu-id="6fbb7-204">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)|<span data-ttu-id="6fbb7-205">描述用于转换、搜索谓词以及要对数组或集合中的元素执行的操作的泛型委托。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-205">Describes generic delegates for conversions, search predicates, and actions to be taken on elements of an array or collection.</span></span>|  
|[<span data-ttu-id="6fbb7-206">泛型接口</span><span class="sxs-lookup"><span data-stu-id="6fbb7-206">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)|<span data-ttu-id="6fbb7-207">描述跨泛型类型系列提供通用功能的泛型接口。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-207">Describes generic interfaces that provide common functionality across families of generic types.</span></span>|  
|[<span data-ttu-id="6fbb7-208">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="6fbb7-208">Covariance and Contravariance</span></span>](../../../docs/standard/generics/covariance-and-contravariance.md)|<span data-ttu-id="6fbb7-209">描述泛型类型实参中的协变和逆变。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-209">Describes covariance and contravariance in generic type parameters.</span></span>|  
|[<span data-ttu-id="6fbb7-210">常用的集合类型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-210">Commonly Used Collection Types</span></span>](../../../docs/standard/collections/commonly-used-collection-types.md)|<span data-ttu-id="6fbb7-211">提供有关 .NET Framework 中集合类型的特征和使用方案的摘要信息，包括泛型类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-211">Provides summary information about the characteristics and usage scenarios of the collection types in the .NET Framework, including generic types.</span></span>|  
|[<span data-ttu-id="6fbb7-212">何时使用泛型集合</span><span class="sxs-lookup"><span data-stu-id="6fbb7-212">When to Use Generic Collections</span></span>](../../../docs/standard/collections/when-to-use-generic-collections.md)|<span data-ttu-id="6fbb7-213">描述用于确定何时使用泛型集合类型的一般规则。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-213">Describes general rules for determining when to use generic collection types.</span></span>|  
|[<span data-ttu-id="6fbb7-214">如何：使用 Reflection Emit 定义泛型类型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-214">How to: Define a Generic Type with Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)|<span data-ttu-id="6fbb7-215">解释如何生成包括泛型类型和方法的动态程序集。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-215">Explains how to generate dynamic assemblies that include generic types and methods.</span></span>|  
|[<span data-ttu-id="6fbb7-216">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="6fbb7-216">Generic Types in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/generic-types.md)|<span data-ttu-id="6fbb7-217">为 Visual Basic 用户描述泛型功能，包括有关使用和定义泛型类型的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-217">Describes the generics feature for Visual Basic users, including how-to topics for using and defining generic types.</span></span>|  
|[<span data-ttu-id="6fbb7-218">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="6fbb7-218">Introduction to Generics</span></span>](~/docs/csharp/programming-guide/generics/introduction-to-generics.md)|<span data-ttu-id="6fbb7-219">为 C# 用户概述定义和使用泛型类型。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-219">Provides an overview of defining and using generic types for C# users.</span></span>|  
|[<span data-ttu-id="6fbb7-220">Visual C++ 中的泛型概述</span><span class="sxs-lookup"><span data-stu-id="6fbb7-220">Overview of Generics in Visual C++</span></span>](http://msdn.microsoft.com/library/21f10637-0fce-4916-b925-6c86a126d3aa)|<span data-ttu-id="6fbb7-221">为 C++ 用户描述泛型功能，包括泛型和模板之间的差异。</span><span class="sxs-lookup"><span data-stu-id="6fbb7-221">Describes the generics feature for C++ users, including the differences between generics and templates.</span></span>|  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="6fbb7-222">参考</span><span class="sxs-lookup"><span data-stu-id="6fbb7-222">Reference</span></span>  
 <span data-ttu-id="6fbb7-223"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="6fbb7-223"><xref:System.Collections.Generic></span></span>  
  
 <span data-ttu-id="6fbb7-224"><xref:System.Collections.ObjectModel></span><span class="sxs-lookup"><span data-stu-id="6fbb7-224"><xref:System.Collections.ObjectModel></span></span>  
  
 <span data-ttu-id="6fbb7-225"><xref:System.Reflection.Emit.OpCodes?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6fbb7-225"><xref:System.Reflection.Emit.OpCodes?displayProperty=fullName></span></span>  
  
 [<span data-ttu-id="6fbb7-226">返回页首</span><span class="sxs-lookup"><span data-stu-id="6fbb7-226">Back to top</span></span>](#top)
