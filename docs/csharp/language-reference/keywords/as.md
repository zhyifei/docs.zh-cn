---
title: as（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 092c30a858df7baeb35bdf28bae53802fb0916d4
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172014"
---
# <a name="as-c-reference"></a><span data-ttu-id="95383-102">as（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="95383-102">as (C# Reference)</span></span>
<span data-ttu-id="95383-103">可以使用 `as` 运算符在符合的引用类型或[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)之间执行某些类型的转换。</span><span class="sxs-lookup"><span data-stu-id="95383-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="95383-104">以下代码显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="95383-104">The following code shows an example.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="95383-105">备注</span><span class="sxs-lookup"><span data-stu-id="95383-105">Remarks</span></span>  
 <span data-ttu-id="95383-106">`as` 运算符类似于转换运算。</span><span class="sxs-lookup"><span data-stu-id="95383-106">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="95383-107">但是，如果无法进行转换，则 `as` 会返回 `null`，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="95383-107">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="95383-108">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="95383-108">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="95383-109">该代码等效于以下表达式，但 `expression` 变量仅进行一次计算。</span><span class="sxs-lookup"><span data-stu-id="95383-109">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="95383-110">请注意，`as` 运算符仅执行引用转换、可以为 null 的转换和装箱转换。</span><span class="sxs-lookup"><span data-stu-id="95383-110">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="95383-111">`as` 运算符无法执行其他转换，例如用户定义的转换，应使用转换表达式执行此转换。</span><span class="sxs-lookup"><span data-stu-id="95383-111">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95383-112">示例</span><span class="sxs-lookup"><span data-stu-id="95383-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="95383-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="95383-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95383-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="95383-114">See Also</span></span>  
 [<span data-ttu-id="95383-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="95383-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="95383-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="95383-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="95383-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="95383-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="95383-118">is</span><span class="sxs-lookup"><span data-stu-id="95383-118">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="95383-119">?: 运算符</span><span class="sxs-lookup"><span data-stu-id="95383-119">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
 [<span data-ttu-id="95383-120">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="95383-120">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
