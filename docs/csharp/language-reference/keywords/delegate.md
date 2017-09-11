---
title: "委托（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="delegate-c-reference"></a><span data-ttu-id="0bf46-102">委托（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0bf46-102">delegate (C# Reference)</span></span>
<span data-ttu-id="0bf46-103">委托类型的声明与方法签名相似。</span><span class="sxs-lookup"><span data-stu-id="0bf46-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="0bf46-104">它有一个返回值和任意数目任意类型的参数：</span><span class="sxs-lookup"><span data-stu-id="0bf46-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="0bf46-105">`delegate` 是一种可用于封装命名方法或匿名方法的引用类型。</span><span class="sxs-lookup"><span data-stu-id="0bf46-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="0bf46-106">委托类似于 C++ 中的函数指针；但是，委托是类型安全和可靠的。</span><span class="sxs-lookup"><span data-stu-id="0bf46-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="0bf46-107">有关委托的应用，请参阅[委托](../../../csharp/programming-guide/delegates/index.md)和[泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="0bf46-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bf46-108">备注</span><span class="sxs-lookup"><span data-stu-id="0bf46-108">Remarks</span></span>  
 <span data-ttu-id="0bf46-109">委托是[事件](../../../csharp/programming-guide/events/index.md)的基础。</span><span class="sxs-lookup"><span data-stu-id="0bf46-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="0bf46-110">通过将委托与命名方法或匿名方法关联，可以实例化委托。</span><span class="sxs-lookup"><span data-stu-id="0bf46-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="0bf46-111">有关详细信息，请参阅[命名方法](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)和[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="0bf46-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="0bf46-112">必须使用具有兼容返回类型和输入参数的方法或 lambda 表达式实例化委托。</span><span class="sxs-lookup"><span data-stu-id="0bf46-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="0bf46-113">有关方法签名中允许的差异程度的详细信息，请参阅[委托中的变体](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca)。</span><span class="sxs-lookup"><span data-stu-id="0bf46-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span></span> <span data-ttu-id="0bf46-114">为了与匿名方法一起使用，委托和与之关联的代码必须一起声明。</span><span class="sxs-lookup"><span data-stu-id="0bf46-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="0bf46-115">本节讨论这两种实例化委托的方法。</span><span class="sxs-lookup"><span data-stu-id="0bf46-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bf46-116">示例</span><span class="sxs-lookup"><span data-stu-id="0bf46-116">Example</span></span>  
 <span data-ttu-id="0bf46-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0bf46-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0bf46-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0bf46-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0bf46-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf46-119">See Also</span></span>  
 <span data-ttu-id="0bf46-120">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0bf46-121">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0bf46-122">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0bf46-123">[引用类型](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-123">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="0bf46-124">[委托](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-124">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="0bf46-125">[事件](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-125">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="0bf46-126">[带有命名方法的委托与匿名方法](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="0bf46-126">[Delegates with Named vs. Anonymous Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span></span>  
 [<span data-ttu-id="0bf46-127">匿名方法</span><span class="sxs-lookup"><span data-stu-id="0bf46-127">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

