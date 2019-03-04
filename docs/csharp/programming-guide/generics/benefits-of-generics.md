---
title: 泛型优势 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
ms.openlocfilehash: 7f882bcdf5c1d9b8c81531c0fe37a3ee27c2e3a0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965406"
---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="fa965-102">泛型的优点（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fa965-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="fa965-103">公共语言运行时和 C# 语言早期版本中存在一个局限，其中通过将类型与通用基类型 <xref:System.Object> 相互强制完成泛化，泛型提供了此局限的解决方案。</span><span class="sxs-lookup"><span data-stu-id="fa965-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="fa965-104">通过创建泛型类，可在编译时创建类型安全的集合。</span><span class="sxs-lookup"><span data-stu-id="fa965-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="fa965-105">通过编写一个使用 .NET 类库中 <xref:System.Collections.ArrayList> 集合类的小程序，可体现出使用非泛型集合类的局限。</span><span class="sxs-lookup"><span data-stu-id="fa965-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET class library.</span></span> <span data-ttu-id="fa965-106"><xref:System.Collections.ArrayList> 类的实例可以存储任何引用或值类型。</span><span class="sxs-lookup"><span data-stu-id="fa965-106">An instance of the <xref:System.Collections.ArrayList> class can store any reference or value type.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#4)]  
  
 <span data-ttu-id="fa965-107">但这种便利有一定代价。</span><span class="sxs-lookup"><span data-stu-id="fa965-107">But this convenience comes at a cost.</span></span> <span data-ttu-id="fa965-108">添加到 <xref:System.Collections.ArrayList> 的任何引用或值类型均隐式向上转换为 <xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="fa965-108">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="fa965-109">如果项为值类型，将它们添加到列表时必须将其装箱，检索它们时必须取消装箱。</span><span class="sxs-lookup"><span data-stu-id="fa965-109">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="fa965-110">转换与装箱/取消装箱这两种操作都会降低性能；在必须循环访问大型集合的方案中，装箱与取消装箱的影响非常大。</span><span class="sxs-lookup"><span data-stu-id="fa965-110">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="fa965-111">另一局限是缺少编译时类型检查；由于 <xref:System.Collections.ArrayList> 将所有内容都转换为 <xref:System.Object>，因此在编译时无法阻止客户端代码执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="fa965-111">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#5)]  
  
 <span data-ttu-id="fa965-112">虽然在创建异类集合时这完全可以接受，甚至有时是有意为之，但将字符串和 `ints` 合并到单个 <xref:System.Collections.ArrayList> 中更有可能属于编程错误，且此错误在运行时之前不会被检测出。</span><span class="sxs-lookup"><span data-stu-id="fa965-112">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="fa965-113">在 C# 语言 1.0 和 1.1 版中，仅可通过编写自己的类型特定集合来避免 .NET Framework 基类库集合类中出现泛化代码的风险。</span><span class="sxs-lookup"><span data-stu-id="fa965-113">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="fa965-114">当然，由于这样的类不能重复用于多个数据类型，因此你并不具有泛化的优势，且必须为要存储的每个类型重写类。</span><span class="sxs-lookup"><span data-stu-id="fa965-114">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="fa965-115"><xref:System.Collections.ArrayList> 以及其他相似的类真正需要的是一种方式，这种方式使客户端代码基于每个实例指定打算使用的特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="fa965-115">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="fa965-116">这会省去向上转换为 <xref:System.Object> 的必要，并且使编译器可能执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="fa965-116">That would eliminate the need for the upcast to <xref:System.Object> and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="fa965-117">换而言之，<xref:System.Collections.ArrayList> 需要一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="fa965-117">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="fa965-118">那正是泛型所提供的内容。</span><span class="sxs-lookup"><span data-stu-id="fa965-118">That is exactly what generics provide.</span></span> <span data-ttu-id="fa965-119">在泛型 <xref:System.Collections.Generic.List%601> 集合中，在 <xref:System.Collections.Generic> 命名空间中，向集合添加项的操作类似于如下所示：</span><span class="sxs-lookup"><span data-stu-id="fa965-119">In the generic <xref:System.Collections.Generic.List%601> collection, in the <xref:System.Collections.Generic> namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#6)]  
  
 <span data-ttu-id="fa965-120">对于客户端代码，与 <xref:System.Collections.ArrayList> 相比，<xref:System.Collections.Generic.List%601> 添加的唯一语法是声明和实例化中的类型参数。</span><span class="sxs-lookup"><span data-stu-id="fa965-120">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="fa965-121">虽然编码略为复杂，但与 <xref:System.Collections.ArrayList> 相比，你创建的列表不仅更加安全，而且创建速度大为提高，尤其是在列表项为值类型时。</span><span class="sxs-lookup"><span data-stu-id="fa965-121">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa965-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa965-122">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="fa965-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fa965-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fa965-124">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="fa965-124">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [<span data-ttu-id="fa965-125">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="fa965-125">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
- [<span data-ttu-id="fa965-126">何时使用泛型集合</span><span class="sxs-lookup"><span data-stu-id="fa965-126">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
- [<span data-ttu-id="fa965-127">集合准则</span><span class="sxs-lookup"><span data-stu-id="fa965-127">Guidelines for Collections</span></span>](../../../standard/design-guidelines/guidelines-for-collections.md)
