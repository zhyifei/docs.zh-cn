---
title: as - C# 参考
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: b87e75bd4866a191e84465e44d53850e6e2e9723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169918"
---
# <a name="as-c-reference"></a><span data-ttu-id="fcb52-102">as（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fcb52-102">as (C# Reference)</span></span>
<span data-ttu-id="fcb52-103">可以使用 `as` 运算符在符合的引用类型或[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)之间执行某些类型的转换。</span><span class="sxs-lookup"><span data-stu-id="fcb52-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="fcb52-104">以下代码显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="fcb52-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="fcb52-105">如示例所示，需要比较 `as` 表达式和 `null` 的结果以检查转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="fcb52-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="fcb52-106">从 C# 7.0 开始，可以使用 [is](is.md) 表达式来测试转换是否成功，并在转换成功时有条件地分配变量。</span><span class="sxs-lookup"><span data-stu-id="fcb52-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="fcb52-107">在许多情况下，它比使用 `as` 运算符更简洁。</span><span class="sxs-lookup"><span data-stu-id="fcb52-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="fcb52-108">有关详细信息，请参阅 [`is` 运算符](is.md)一文中的[类型模式](is.md#type)部分。</span><span class="sxs-lookup"><span data-stu-id="fcb52-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fcb52-109">备注</span><span class="sxs-lookup"><span data-stu-id="fcb52-109">Remarks</span></span>  
 <span data-ttu-id="fcb52-110">`as` 运算符类似于转换运算。</span><span class="sxs-lookup"><span data-stu-id="fcb52-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="fcb52-111">但是，如果无法进行转换，则 `as` 会返回 `null`，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="fcb52-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="fcb52-112">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="fcb52-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="fcb52-113">该代码等效于以下表达式，但 `expression` 变量仅进行一次计算。</span><span class="sxs-lookup"><span data-stu-id="fcb52-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="fcb52-114">请注意，`as` 运算符仅执行引用转换、可以为 null 的转换和装箱转换。</span><span class="sxs-lookup"><span data-stu-id="fcb52-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="fcb52-115">`as` 运算符无法执行其他转换，例如用户定义的转换，应使用转换表达式执行此转换。</span><span class="sxs-lookup"><span data-stu-id="fcb52-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcb52-116">示例</span><span class="sxs-lookup"><span data-stu-id="fcb52-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="fcb52-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fcb52-117">C# Language Specification</span></span>  

<span data-ttu-id="fcb52-118">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [As 运算符](~/_csharplang/spec/expressions.md#the-as-operator)。</span><span class="sxs-lookup"><span data-stu-id="fcb52-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="fcb52-119">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="fcb52-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="fcb52-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcb52-120">See also</span></span>

- [<span data-ttu-id="fcb52-121">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fcb52-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="fcb52-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fcb52-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fcb52-123">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="fcb52-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="fcb52-124">is</span><span class="sxs-lookup"><span data-stu-id="fcb52-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="fcb52-125">?:运算符</span><span class="sxs-lookup"><span data-stu-id="fcb52-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)
- [<span data-ttu-id="fcb52-126">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="fcb52-126">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
