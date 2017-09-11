---
title: "as（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
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
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="as-c-reference"></a><span data-ttu-id="6ac2f-102">as（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6ac2f-102">as (C# Reference)</span></span>
<span data-ttu-id="6ac2f-103">可以使用 `as` 运算符在符合的引用类型或[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)之间执行某些类型的转换。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="6ac2f-104">以下代码显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-104">The following code shows an example.</span></span>  
  
 <span data-ttu-id="6ac2f-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ac2f-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ac2f-106">备注</span><span class="sxs-lookup"><span data-stu-id="6ac2f-106">Remarks</span></span>  
 <span data-ttu-id="6ac2f-107">`as` 运算符类似于转换运算。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-107">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="6ac2f-108">但是，如果无法进行转换，则 `as` 会返回 `null`，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-108">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="6ac2f-109">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="6ac2f-109">Consider the following example:</span></span>  
  
```  
expression as type  
```  
  
 <span data-ttu-id="6ac2f-110">该代码等效于以下表达式，但 `expression` 变量仅进行一次计算。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-110">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="6ac2f-111">请注意，`as` 运算符仅执行引用转换、可以为 null 的转换和装箱转换。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-111">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="6ac2f-112">`as` 运算符无法执行其他转换，例如用户定义的转换，应使用转换表达式执行此转换。</span><span class="sxs-lookup"><span data-stu-id="6ac2f-112">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ac2f-113">示例</span><span class="sxs-lookup"><span data-stu-id="6ac2f-113">Example</span></span>  
 <span data-ttu-id="6ac2f-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ac2f-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ac2f-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6ac2f-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ac2f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ac2f-116">See Also</span></span>  
 <span data-ttu-id="6ac2f-117">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ac2f-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6ac2f-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ac2f-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6ac2f-119">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ac2f-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6ac2f-120">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="6ac2f-120">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="6ac2f-121">[?: 运算符](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6ac2f-121">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 [<span data-ttu-id="6ac2f-122">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="6ac2f-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

