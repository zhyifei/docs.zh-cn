---
title: "泛型（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: de81058173b0985577474e8601aa84d4e83336a5
ms.contentlocale: zh-cn
ms.lasthandoff: 08/29/2017

---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="cf923-102">泛型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="cf923-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="cf923-103">C# 语言和公共语言运行时 (CLR) 的 2.0 版本中添加了泛型。</span><span class="sxs-lookup"><span data-stu-id="cf923-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="cf923-104">泛型将类型参数的概念引入 .NET Framework，这样就可以设计具有以下特征的类和方法：在客户端代码声明并初始化这些类和方法之前，这些类和方法会延迟指定一个或多个类型。</span><span class="sxs-lookup"><span data-stu-id="cf923-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="cf923-105">例如，通过使用泛型类型参数 T，可以编写其他客户端代码能够使用的单个类，而不会产生运行时转换或装箱操作的成本或风险，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf923-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 <span data-ttu-id="cf923-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf923-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="generics-overview"></a><span data-ttu-id="cf923-107">泛型概述</span><span class="sxs-lookup"><span data-stu-id="cf923-107">Generics Overview</span></span>  
  
-   <span data-ttu-id="cf923-108">使用泛型类型可以最大限度地重用代码、保护类型安全性以及提高性能。</span><span class="sxs-lookup"><span data-stu-id="cf923-108">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="cf923-109">泛型最常见的用途是创建集合类。</span><span class="sxs-lookup"><span data-stu-id="cf923-109">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="cf923-110">.NET Framework 类库在 <xref:System.Collections.Generic> 命名空间中包含几个新的泛型集合类。</span><span class="sxs-lookup"><span data-stu-id="cf923-110">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="cf923-111">应尽可能使用这些类来代替某些类，如 <xref:System.Collections> 命名空间中的 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="cf923-111">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="cf923-112">可以创建自己的泛型接口、泛型类、泛型方法、泛型事件和泛型委托。</span><span class="sxs-lookup"><span data-stu-id="cf923-112">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="cf923-113">可以对泛型类进行约束以访问特定数据类型的方法。</span><span class="sxs-lookup"><span data-stu-id="cf923-113">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="cf923-114">在泛型数据类型中所用类型的信息可在运行时通过使用反射来获取。</span><span class="sxs-lookup"><span data-stu-id="cf923-114">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cf923-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="cf923-115">Related Sections</span></span>  
 <span data-ttu-id="cf923-116">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="cf923-116">For more information:</span></span>  
  
-   [<span data-ttu-id="cf923-117">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="cf923-117">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="cf923-118">泛型的优点</span><span class="sxs-lookup"><span data-stu-id="cf923-118">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="cf923-119">泛型类型参数</span><span class="sxs-lookup"><span data-stu-id="cf923-119">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="cf923-120">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="cf923-120">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="cf923-121">泛型类</span><span class="sxs-lookup"><span data-stu-id="cf923-121">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="cf923-122">泛型接口</span><span class="sxs-lookup"><span data-stu-id="cf923-122">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="cf923-123">泛型方法</span><span class="sxs-lookup"><span data-stu-id="cf923-123">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="cf923-124">泛型委托</span><span class="sxs-lookup"><span data-stu-id="cf923-124">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="cf923-125">C++ 模板和 C# 泛型之间的区别</span><span class="sxs-lookup"><span data-stu-id="cf923-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="cf923-126">泛型和反射</span><span class="sxs-lookup"><span data-stu-id="cf923-126">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="cf923-127">运行时中的泛型</span><span class="sxs-lookup"><span data-stu-id="cf923-127">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [<span data-ttu-id="cf923-128">.NET Framework 类库中的泛型</span><span class="sxs-lookup"><span data-stu-id="cf923-128">Generics in the .NET Framework Class Library</span></span>](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="cf923-129">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="cf923-129">C# Language Specification</span></span>  
 <span data-ttu-id="cf923-130">有关详细信息，请参阅 [C# 语言规范](../../../csharp/language-reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf923-130">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf923-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf923-131">See Also</span></span>  
 <span data-ttu-id="cf923-132"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="cf923-132"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="cf923-133">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf923-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cf923-134">[类型](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf923-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="cf923-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span><span class="sxs-lookup"><span data-stu-id="cf923-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span></span>  
 [<span data-ttu-id="cf923-136">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="cf923-136">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)

