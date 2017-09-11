---
title: "=&gt; 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 45d4753724ed094408e8cbc5353998a67071b0e4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="cb99d-102">=&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="cb99d-102">=&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="cb99d-103">`=>` 标记称作 lambda 运算符。</span><span class="sxs-lookup"><span data-stu-id="cb99d-103">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="cb99d-104">该标记在 Lambda 表达式中用来将左侧的输入变量与右侧的 lambda 体分离。</span><span class="sxs-lookup"><span data-stu-id="cb99d-104">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="cb99d-105">Lambda 表达式是类似于匿名方法的内联表达式，但更加灵活；在以方法语法表示的 LINQ 查询中广泛使用了 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="cb99d-105">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="cb99d-106">有关详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="cb99d-106">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="cb99d-107">以下示例演示了 2 种在字符串数组中查找并显示最短字符串长度的方法。</span><span class="sxs-lookup"><span data-stu-id="cb99d-107">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="cb99d-108">本示例的第一部分将 Lambda 表达式 (`w => w.Length`) 应用于 `words` 数组的每个元素中，然后使用 <xref:System.Linq.Enumerable.Min%2A> 方法查找最小长度。</span><span class="sxs-lookup"><span data-stu-id="cb99d-108">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="cb99d-109">为了进行比较，本示例的第二部分演示了使用查询语法执行相同操作的较长解决方案。</span><span class="sxs-lookup"><span data-stu-id="cb99d-109">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
## <a name="remarks"></a><span data-ttu-id="cb99d-110">备注</span><span class="sxs-lookup"><span data-stu-id="cb99d-110">Remarks</span></span>  
 <span data-ttu-id="cb99d-111">`=>` 运算符具有与赋值运算符 (`=`) 相同的优先级，并且是右结合运算符。</span><span class="sxs-lookup"><span data-stu-id="cb99d-111">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="cb99d-112">可以显式指定输入变量的类型或让编译器推断类型；无论何种情况，该变量在编译时均为强类型。</span><span class="sxs-lookup"><span data-stu-id="cb99d-112">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="cb99d-113">指定类型时，必须用括号括住类型名称和变量名称，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cb99d-113">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a><span data-ttu-id="cb99d-114">示例</span><span class="sxs-lookup"><span data-stu-id="cb99d-114">Example</span></span>  
 <span data-ttu-id="cb99d-115">以下示例演示如何为使用 2 个参数的标准查询运算符 <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> 的重载编写一个 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="cb99d-115">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> that takes two arguments.</span></span> <span data-ttu-id="cb99d-116">由于 Lambda 表达式具有多个参数，因此参数必须括在括号中。</span><span class="sxs-lookup"><span data-stu-id="cb99d-116">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="cb99d-117">第 2 个参数 `index` 表示集合中当前元素的索引。</span><span class="sxs-lookup"><span data-stu-id="cb99d-117">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="cb99d-118">`Where` 表达式返回长度小于其数组中索引位置的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="cb99d-118">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb99d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb99d-119">See Also</span></span>  
 <span data-ttu-id="cb99d-120">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cb99d-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cb99d-121">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cb99d-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="cb99d-122">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="cb99d-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

