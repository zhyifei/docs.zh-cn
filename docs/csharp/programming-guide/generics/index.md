---
title: '泛型 - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
  - 'C# language, generics'
  - 'generics [C#]'
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="50b4f-102">泛型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="50b4f-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="50b4f-103">C# 语言和公共语言运行时 (CLR) 的 2.0 版本中添加了泛型。</span><span class="sxs-lookup"><span data-stu-id="50b4f-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="50b4f-104">泛型将类型参数的概念引入 .NET Framework，这样就可以设计具有以下特征的类和方法：在客户端代码声明并初始化这些类和方法之前，这些类和方法会延迟指定一个或多个类型。</span><span class="sxs-lookup"><span data-stu-id="50b4f-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="50b4f-105">例如，通过使用泛型类型参数 T，可以编写其他客户端代码能够使用的单个类，而不会产生运行时转换或装箱操作的成本或风险，如下所示：</span><span class="sxs-lookup"><span data-stu-id="50b4f-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  
  
## <a name="generics-overview"></a><span data-ttu-id="50b4f-106">泛型概述</span><span class="sxs-lookup"><span data-stu-id="50b4f-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="50b4f-107">使用泛型类型可以最大限度地重用代码、保护类型安全性以及提高性能。</span><span class="sxs-lookup"><span data-stu-id="50b4f-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="50b4f-108">泛型最常见的用途是创建集合类。</span><span class="sxs-lookup"><span data-stu-id="50b4f-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="50b4f-109">.NET Framework 类库在 <xref:System.Collections.Generic> 命名空间中包含几个新的泛型集合类。</span><span class="sxs-lookup"><span data-stu-id="50b4f-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="50b4f-110">应尽可能使用这些类来代替某些类，如 <xref:System.Collections> 命名空间中的 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="50b4f-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="50b4f-111">可以创建自己的泛型接口、泛型类、泛型方法、泛型事件和泛型委托。</span><span class="sxs-lookup"><span data-stu-id="50b4f-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="50b4f-112">可以对泛型类进行约束以访问特定数据类型的方法。</span><span class="sxs-lookup"><span data-stu-id="50b4f-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="50b4f-113">在泛型数据类型中所用类型的信息可在运行时通过使用反射来获取。</span><span class="sxs-lookup"><span data-stu-id="50b4f-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50b4f-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="50b4f-114">Related Sections</span></span>  
 <span data-ttu-id="50b4f-115">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="50b4f-115">For more information:</span></span>  
  
-   [<span data-ttu-id="50b4f-116">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="50b4f-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="50b4f-117">泛型的优点</span><span class="sxs-lookup"><span data-stu-id="50b4f-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="50b4f-118">泛型类型参数</span><span class="sxs-lookup"><span data-stu-id="50b4f-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="50b4f-119">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="50b4f-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="50b4f-120">泛型类</span><span class="sxs-lookup"><span data-stu-id="50b4f-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="50b4f-121">泛型接口</span><span class="sxs-lookup"><span data-stu-id="50b4f-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="50b4f-122">泛型方法</span><span class="sxs-lookup"><span data-stu-id="50b4f-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="50b4f-123">泛型委托</span><span class="sxs-lookup"><span data-stu-id="50b4f-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="50b4f-124">C++ 模板和 C# 泛型之间的区别</span><span class="sxs-lookup"><span data-stu-id="50b4f-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="50b4f-125">泛型和反射</span><span class="sxs-lookup"><span data-stu-id="50b4f-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="50b4f-126">运行时中的泛型</span><span class="sxs-lookup"><span data-stu-id="50b4f-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="50b4f-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="50b4f-127">C# Language Specification</span></span>  
 <span data-ttu-id="50b4f-128">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/types.md#constructed-types)。</span><span class="sxs-lookup"><span data-stu-id="50b4f-128">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b4f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="50b4f-129">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="50b4f-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="50b4f-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="50b4f-131">类型</span><span class="sxs-lookup"><span data-stu-id="50b4f-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="50b4f-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="50b4f-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="50b4f-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="50b4f-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="50b4f-134">.NET 中的泛型</span><span class="sxs-lookup"><span data-stu-id="50b4f-134">Generics in .NET</span></span>](../../../standard/generics/index.md)
