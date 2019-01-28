---
title: 泛型类型参数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 48fa90226b7a8a36f5f432921cf5d999e76c6fa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681633"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="59430-102">泛型类型参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="59430-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="59430-103">在泛型类型或方法定义中，类型参数是在其实例化泛型类型的一个变量时，客户端指定的特定类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="59430-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="59430-104">泛型类（例如[泛型介绍](../../../csharp/programming-guide/generics/introduction-to-generics.md)中列出的 `GenericList<T>`）无法按原样使用，因为它不是真正的类型；它更像是类型的蓝图。</span><span class="sxs-lookup"><span data-stu-id="59430-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="59430-105">若要使用 `GenericList<T>`，客户端代码必须通过指定尖括号内的类型参数来声明并实例化构造类型。</span><span class="sxs-lookup"><span data-stu-id="59430-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="59430-106">此特定类的类型参数可以是编译器可识别的任何类型。</span><span class="sxs-lookup"><span data-stu-id="59430-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="59430-107">可创建任意数量的构造类型实例，其中每个使用不同的类型参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59430-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 <span data-ttu-id="59430-108">在 `GenericList<T>` 的每个实例中，类中出现的每个 `T` 在运行时均会被替换为类型参数。</span><span class="sxs-lookup"><span data-stu-id="59430-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="59430-109">通过这种替换，我们已通过使用单个类定义创建了三个单独的类型安全的有效对象。</span><span class="sxs-lookup"><span data-stu-id="59430-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="59430-110">有关 CLR 如何执行此替换的详细信息，请参阅[运行时中的泛型](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)。</span><span class="sxs-lookup"><span data-stu-id="59430-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="59430-111">类型参数命名指南</span><span class="sxs-lookup"><span data-stu-id="59430-111">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="59430-112">请使用描述性名称命名泛型类型参数，除非单个字母名称完全具有自我说明性且描述性名称不会增加任何作用。</span><span class="sxs-lookup"><span data-stu-id="59430-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   <span data-ttu-id="59430-113">对具有单个字母类型参数的类型，考虑使用 T 作为类型参数名称。</span><span class="sxs-lookup"><span data-stu-id="59430-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   <span data-ttu-id="59430-114">在类型参数描述性名称前添加前缀 "T"。</span><span class="sxs-lookup"><span data-stu-id="59430-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   <span data-ttu-id="59430-115">请考虑在参数名称中指示出类型参数的约束。</span><span class="sxs-lookup"><span data-stu-id="59430-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="59430-116">例如，约束为 `ISession` 的参数可命名为 `TSession`。</span><span class="sxs-lookup"><span data-stu-id="59430-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59430-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="59430-117">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="59430-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="59430-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="59430-119">泛型</span><span class="sxs-lookup"><span data-stu-id="59430-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="59430-120">C++ 模板和 C# 泛型之间的区别</span><span class="sxs-lookup"><span data-stu-id="59430-120">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
