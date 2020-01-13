---
title: 泛型类型参数 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 8412980d35989c445d2e0a44c0b9f35e6087bb8d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712177"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="f3d4f-102">泛型类型参数 -（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f3d4f-102">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="f3d4f-103">在泛型类型或方法定义中，类型参数是在其创建泛型类型的一个实例时，客户端指定的特定类型的占位符。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-103">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="f3d4f-104">泛型类（例如[泛型介绍](./index.md)中列出的 `GenericList<T>`）无法按原样使用，因为它不是真正的类型；它更像是类型的蓝图。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="f3d4f-105">若要使用 `GenericList<T>`，客户端代码必须通过指定尖括号内的类型参数来声明并实例化构造类型。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="f3d4f-106">此特定类的类型参数可以是编译器可识别的任何类型。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="f3d4f-107">可创建任意数量的构造类型实例，其中每个使用不同的类型参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f3d4f-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="f3d4f-108">在 `GenericList<T>` 的每个实例中，类中出现的每个 `T` 在运行时均会被替换为类型参数。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="f3d4f-109">通过这种替换，我们已通过使用单个类定义创建了三个单独的类型安全的有效对象。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="f3d4f-110">有关 CLR 如何执行此替换的详细信息，请参阅[运行时中的泛型](./generics-in-the-run-time.md)。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="f3d4f-111">类型参数命名指南</span><span class="sxs-lookup"><span data-stu-id="f3d4f-111">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="f3d4f-112">请使用描述性名称命名泛型类型参数  ，除非单个字母名称完全具有自我说明性且描述性名称不会增加任何作用。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="f3d4f-113">对具有单个字母类型参数的类型，考虑使用 T 作为类型参数名称  。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="f3d4f-114">在类型参数描述性名称前添加前缀 "T"  。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="f3d4f-115">请考虑在参数名称中指示出类型参数的约束  。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="f3d4f-116">例如，约束为 `ISession` 的参数可命名为 `TSession`。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="f3d4f-117">可以使用代码分析规则 [CA1715](/visualstudio/code-quality/ca1715) 确保恰当地命名类型参数。</span><span class="sxs-lookup"><span data-stu-id="f3d4f-117">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f3d4f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3d4f-118">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="f3d4f-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f3d4f-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f3d4f-120">泛型</span><span class="sxs-lookup"><span data-stu-id="f3d4f-120">Generics</span></span>](./index.md)
- [<span data-ttu-id="f3d4f-121">C++ 模板和 C# 泛型之间的区别</span><span class="sxs-lookup"><span data-stu-id="f3d4f-121">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
