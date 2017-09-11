---
title: "泛型的优点（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b05a3a695064764618564293e6ccd92e2ce60be
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="2bcb1-102">泛型的优点（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2bcb1-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="2bcb1-103">公共语言运行时和 C# 语言早期版本中存在一个局限，其中通过将类型与通用基类型 <xref:System.Object> 相互强制完成泛化，泛型提供了此局限的解决方案。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="2bcb1-104">通过创建泛型类，可在编译时创建类型安全的集合。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="2bcb1-105">通过编写一个使用 .NET Framework 类库中 <xref:System.Collections.ArrayList> 集合类的小程序，可体现出使用非泛型集合类的局限。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET Framework class library.</span></span> <span data-ttu-id="2bcb1-106"><xref:System.Collections.ArrayList> 是一个极为方便的集合类，无需进行修改即可用于存储任何引用或值类型。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-106"><xref:System.Collections.ArrayList> is a highly convenient collection class that can be used without modification to store any reference or value type.</span></span>  
  
 <span data-ttu-id="2bcb1-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2bcb1-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span></span>  
  
 <span data-ttu-id="2bcb1-108">但这种便利有一定代价。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-108">But this convenience comes at a cost.</span></span> <span data-ttu-id="2bcb1-109">添加到 <xref:System.Collections.ArrayList> 的任何引用或值类型均隐式向上转换为 <xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-109">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="2bcb1-110">如果项为值类型，将它们添加到列表时必须将其装箱，检索它们时必须取消装箱。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-110">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="2bcb1-111">转换与装箱/取消装箱这两种操作都会降低性能；在必须循环访问大型集合的方案中，装箱与取消装箱的影响非常大。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-111">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="2bcb1-112">另一局限是缺少编译时类型检查；由于 <xref:System.Collections.ArrayList> 将所有内容都转换为 <xref:System.Object>，因此在编译时无法阻止客户端代码执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="2bcb1-112">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 <span data-ttu-id="2bcb1-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2bcb1-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span></span>  
  
 <span data-ttu-id="2bcb1-114">虽然在创建异类集合时这完全可以接受，甚至有时是有意为之，但将字符串和 `ints` 合并到单个 <xref:System.Collections.ArrayList> 中更有可能属于编程错误，且此错误在运行时之前不会被检测出。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-114">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="2bcb1-115">在 C# 语言 1.0 和 1.1 版中，仅可通过编写自己的类型特定集合来避免 .NET Framework 基类库集合类中出现泛化代码的风险。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-115">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="2bcb1-116">当然，由于这样的类不能重复用于多个数据类型，因此你并不具有泛化的优势，且必须为要存储的每个类型重写类。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-116">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="2bcb1-117"><xref:System.Collections.ArrayList> 以及其他相似的类真正需要的是一种方式，这种方式使客户端代码基于每个实例指定打算使用的特定数据类型。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-117">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="2bcb1-118">这会省去向上转换为 `T:System.Object` 的必要，并且使编译器可能执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-118">That would eliminate the need for the upcast to `T:System.Object` and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="2bcb1-119">换而言之，<xref:System.Collections.ArrayList> 需要一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-119">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="2bcb1-120">那正是泛型所提供的内容。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-120">That is exactly what generics provide.</span></span> <span data-ttu-id="2bcb1-121">在泛型 <xref:System.Collections.Generic.List%601> 集合中，在 `N:System.Collections.Generic` 命名空间中，向集合添加项的操作类似于如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bcb1-121">In the generic <xref:System.Collections.Generic.List%601> collection, in the `N:System.Collections.Generic` namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 <span data-ttu-id="2bcb1-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2bcb1-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span></span>  
  
 <span data-ttu-id="2bcb1-123">对于客户端代码，与 <xref:System.Collections.ArrayList> 相比，<xref:System.Collections.Generic.List%601> 添加的唯一语法是声明和实例化中的类型参数。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-123">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="2bcb1-124">虽然编码略为复杂，但与 <xref:System.Collections.ArrayList> 相比，你创建的列表不仅更加安全，而且创建速度大为提高，尤其是在列表项为值类型时。</span><span class="sxs-lookup"><span data-stu-id="2bcb1-124">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bcb1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bcb1-125">See Also</span></span>  
 <span data-ttu-id="2bcb1-126"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="2bcb1-126"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="2bcb1-127">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2bcb1-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2bcb1-128">[泛型简介](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="2bcb1-128">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="2bcb1-129">[装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span><span class="sxs-lookup"><span data-stu-id="2bcb1-129">[Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span></span>  
 [<span data-ttu-id="2bcb1-130">最佳实践集合</span><span class="sxs-lookup"><span data-stu-id="2bcb1-130">Collections Best Practices</span></span>](http://go.microsoft.com/fwlink/?LinkId=112403)

