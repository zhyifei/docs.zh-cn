---
title: 如何：使用 foreach 访问集合类（C# 编程指南）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0cf827e958d4dc3b951d17b53effd155356c0ca5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a><span data-ttu-id="06f47-102">如何：使用 foreach 访问集合类（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="06f47-102">How to: Access a Collection Class with foreach (C# Programming Guide)</span></span>
<span data-ttu-id="06f47-103">下面的代码示例演示如何编写可与 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 结合使用的非泛型集合类。</span><span class="sxs-lookup"><span data-stu-id="06f47-103">The following code example illustrates how to write a non-generic collection class that can be used with [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span></span> <span data-ttu-id="06f47-104">该示例定义了字符串 tokenizer 类。</span><span class="sxs-lookup"><span data-stu-id="06f47-104">The example defines a string tokenizer class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06f47-105">此示例介绍的是只在无法使用泛型集合类时才采用的推荐做法。</span><span class="sxs-lookup"><span data-stu-id="06f47-105">This example represents recommended practice only when you cannot use a generic collection class.</span></span> <span data-ttu-id="06f47-106">有关如何实现支持 <xref:System.Collections.Generic.IEnumerable%601> 的类型安全的泛型集合类，请参阅[迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)。</span><span class="sxs-lookup"><span data-stu-id="06f47-106">For an example of how to implement a type-safe generic collection class that supports <xref:System.Collections.Generic.IEnumerable%601>, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="06f47-107">在该示例中，下面的代码段使用 `Tokens` 类，</span><span class="sxs-lookup"><span data-stu-id="06f47-107">In the example, the following code segment uses the `Tokens` class to break the sentence "This is a sample sentence."</span></span> <span data-ttu-id="06f47-108">通过“ ”和“-”分隔符将句子“This is a sample sentence.”分成若干标记。</span><span class="sxs-lookup"><span data-stu-id="06f47-108">into tokens by using ' ' and '-' as separators.</span></span> <span data-ttu-id="06f47-109">然后，该代码使用 `foreach` 语句显示这些标记。</span><span class="sxs-lookup"><span data-stu-id="06f47-109">The code then displays those tokens by using a `foreach` statement.</span></span>  
  
 [!code-csharp[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="06f47-110">示例</span><span class="sxs-lookup"><span data-stu-id="06f47-110">Example</span></span>  
 <span data-ttu-id="06f47-111">在内部，`Tokens` 类使用数组存储这些标记。</span><span class="sxs-lookup"><span data-stu-id="06f47-111">Internally, the `Tokens` class uses an array to store the tokens.</span></span> <span data-ttu-id="06f47-112">数组实现 <xref:System.Collections.IEnumerator> 和 <xref:System.Collections.IEnumerable>，因此，此代码示例本可以使用数组的枚举方法（<xref:System.Collections.IEnumerable.GetEnumerator%2A>、<xref:System.Collections.IEnumerator.MoveNext%2A>、<xref:System.Collections.IEnumerator.Reset%2A> 和 <xref:System.Collections.IEnumerator.Current%2A>），而不是在 `Tokens` 类中对其进行定义。</span><span class="sxs-lookup"><span data-stu-id="06f47-112">Because arrays implement <xref:System.Collections.IEnumerator> and <xref:System.Collections.IEnumerable>, the code example could have used the array's enumeration methods (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>) instead of defining them in the `Tokens` class.</span></span> <span data-ttu-id="06f47-113">方法定义包括在该示例中，用于明确如何定义它们以及每个定义的内容。</span><span class="sxs-lookup"><span data-stu-id="06f47-113">The method definitions are included in the example to clarify how they are defined and what each does.</span></span>  
  
 [!code-csharp[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 <span data-ttu-id="06f47-114">在 C# 中，为兼容 <xref:System.Collections.IEnumerable>，集合类并非一定要实现 <xref:System.Collections.IEnumerator> 和 `foreach`。</span><span class="sxs-lookup"><span data-stu-id="06f47-114">In C#, it is not necessary for a collection class to implement <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> to be compatible with `foreach`.</span></span> <span data-ttu-id="06f47-115">如果类具有所需的 <xref:System.Collections.IEnumerable.GetEnumerator%2A>、<xref:System.Collections.IEnumerator.MoveNext%2A><xref:System.Collections.IEnumerator.Reset%2A> 和 <xref:System.Collections.IEnumerator.Current%2A> 成员，则它将适用于 `foreach`。</span><span class="sxs-lookup"><span data-stu-id="06f47-115">If the class has the required <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A> members, it will work with `foreach`.</span></span> <span data-ttu-id="06f47-116">省略接口有一个好处：可以比 <xref:System.Object> 更为具体地定义 `Current` 的返回类型。</span><span class="sxs-lookup"><span data-stu-id="06f47-116">Omitting the interfaces has the advantage of enabling you to define a return type for `Current` that is more specific than <xref:System.Object>.</span></span> <span data-ttu-id="06f47-117">这提供类型安全性。</span><span class="sxs-lookup"><span data-stu-id="06f47-117">This provides type safety.</span></span>  
  
 <span data-ttu-id="06f47-118">例如，可更改上述示例中的以下行。</span><span class="sxs-lookup"><span data-stu-id="06f47-118">For example, change the following lines in the previous example.</span></span>  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 <span data-ttu-id="06f47-119">由于 `Current` 返回字符串，因此编译器可检测何时在 `foreach` 语句中使用了不兼容的类型，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="06f47-119">Because `Current` returns a string, the compiler can detect when an incompatible type is used in a `foreach` statement, as shown in the following code.</span></span>  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <span data-ttu-id="06f47-120">省略 <xref:System.Collections.IEnumerable> 和 <xref:System.Collections.IEnumerator> 的缺点是：集合类不再可与其他公共语言运行时语言的 `foreach` 语句或等效语句互操作。</span><span class="sxs-lookup"><span data-stu-id="06f47-120">The disadvantage of omitting <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> is that the collection class is no longer interoperable with the `foreach` statements, or equivalent statements, of other common language runtime languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06f47-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06f47-121">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="06f47-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="06f47-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="06f47-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="06f47-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="06f47-124">阵列</span><span class="sxs-lookup"><span data-stu-id="06f47-124">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="06f47-125">集合</span><span class="sxs-lookup"><span data-stu-id="06f47-125">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
