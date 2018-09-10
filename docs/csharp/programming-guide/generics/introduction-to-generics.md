---
title: 泛型介绍（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 17f4c67792732be7a678ec858b6627fa712194c5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861282"
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="dc208-102">泛型介绍（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="dc208-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="dc208-103">泛型类和泛型方法兼具可重用性、类型安全性和效率，这是非泛型类和非泛型方法无法实现的。</span><span class="sxs-lookup"><span data-stu-id="dc208-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="dc208-104">泛型通常与集合以及作用于集合的方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="dc208-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="dc208-105">.NET Framework 2.0 版类库提供新的命名空间 <xref:System.Collections.Generic>，其中包含几个新的基于泛型的集合类。</span><span class="sxs-lookup"><span data-stu-id="dc208-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="dc208-106">建议所有定目标到 .NET Framework 2.0 及更高版本的应用程序都使用新增的泛型集合类，而不是旧的非泛型集合类（如 <xref:System.Collections.ArrayList>）。</span><span class="sxs-lookup"><span data-stu-id="dc208-106">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="dc208-107">有关详细信息，请参阅 [.NET 中的泛型](../../../standard/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="dc208-107">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="dc208-108">当然，也可以创建自定义泛型类型和泛型方法，以提供自己的通用解决方案，设计类型安全的高效模式。</span><span class="sxs-lookup"><span data-stu-id="dc208-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="dc208-109">以下代码示例演示了出于演示目的的简单泛型链接列表类。</span><span class="sxs-lookup"><span data-stu-id="dc208-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="dc208-110">（大多数情况下，应使用 .NET Framework 类库提供的 <xref:System.Collections.Generic.List%601> 类，而不是自行创建类。）在通常使用具体类型来指示列表中所存储项的类型的情况下，可使用类型参数 `T`。</span><span class="sxs-lookup"><span data-stu-id="dc208-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="dc208-111">其使用方法如下：</span><span class="sxs-lookup"><span data-stu-id="dc208-111">It is used in the following ways:</span></span>  
  
-   <span data-ttu-id="dc208-112">在 `AddHead` 方法中作为方法参数的类型。</span><span class="sxs-lookup"><span data-stu-id="dc208-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
-   <span data-ttu-id="dc208-113">在 `Node` 嵌套类中作为 `Data` 属性的返回类型。</span><span class="sxs-lookup"><span data-stu-id="dc208-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
-   <span data-ttu-id="dc208-114">在嵌套类中作为私有成员 `data` 的类型。</span><span class="sxs-lookup"><span data-stu-id="dc208-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="dc208-115">请注意，T 可用于 `Node` 嵌套类。</span><span class="sxs-lookup"><span data-stu-id="dc208-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="dc208-116">如果使用具体类型实例化 `GenericList<T>`（例如，作为 `GenericList<int>`），则出现的所有 `T` 都将替换为 `int`。</span><span class="sxs-lookup"><span data-stu-id="dc208-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 <span data-ttu-id="dc208-117">以下代码示例演示了客户端代码如何使用泛型 `GenericList<T>` 类来创建整数列表。</span><span class="sxs-lookup"><span data-stu-id="dc208-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="dc208-118">只需更改类型参数，即可轻松修改以下代码，创建字符串或任何其他自定义类型的列表：</span><span class="sxs-lookup"><span data-stu-id="dc208-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dc208-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc208-119">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="dc208-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dc208-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dc208-121">泛型</span><span class="sxs-lookup"><span data-stu-id="dc208-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
