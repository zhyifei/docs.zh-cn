---
title: =&gt; 运算符（C# 参考）
ms.date: 10/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="213fc-102">=&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="213fc-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="213fc-103">`=>`运算符可在 C# 中的两种方式：</span><span class="sxs-lookup"><span data-stu-id="213fc-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="213fc-104">作为[lambda 运算符](#lamba-operator)中[lambda 表达式](../../lambda-expressions.md)，它将与 lambda 体分隔输入的变量。</span><span class="sxs-lookup"><span data-stu-id="213fc-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="213fc-105">在[表达式主体定义](#expression-body-definition)，它将成员名称与成员的实现分隔开。</span><span class="sxs-lookup"><span data-stu-id="213fc-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="213fc-106">Lambda 运算符</span><span class="sxs-lookup"><span data-stu-id="213fc-106">Lambda operator</span></span>

<span data-ttu-id="213fc-107">`=>` 标记称作 lambda 运算符。</span><span class="sxs-lookup"><span data-stu-id="213fc-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="213fc-108">该标记在 Lambda 表达式中用来将左侧的输入变量与右侧的 lambda 体分离。</span><span class="sxs-lookup"><span data-stu-id="213fc-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="213fc-109">Lambda 表达式是类似于匿名方法的内联表达式，但更加灵活；在以方法语法表示的 LINQ 查询中广泛使用了 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="213fc-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="213fc-110">有关详细信息，请参阅 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="213fc-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="213fc-111">以下示例演示了 2 种在字符串数组中查找并显示最短字符串长度的方法。</span><span class="sxs-lookup"><span data-stu-id="213fc-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="213fc-112">本示例的第一部分将 Lambda 表达式 (`w => w.Length`) 应用于 `words` 数组的每个元素中，然后使用 <xref:System.Linq.Enumerable.Min%2A> 方法查找最小长度。</span><span class="sxs-lookup"><span data-stu-id="213fc-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="213fc-113">为了进行比较，本示例的第二部分演示了使用查询语法执行相同操作的较长解决方案。</span><span class="sxs-lookup"><span data-stu-id="213fc-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
### <a name="remarks"></a><span data-ttu-id="213fc-114">备注</span><span class="sxs-lookup"><span data-stu-id="213fc-114">Remarks</span></span>  
 <span data-ttu-id="213fc-115">`=>` 运算符具有与赋值运算符 (`=`) 相同的优先级，并且是右结合运算符。</span><span class="sxs-lookup"><span data-stu-id="213fc-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="213fc-116">可以显式指定输入变量的类型或让编译器推断类型；无论何种情况，该变量在编译时均为强类型。</span><span class="sxs-lookup"><span data-stu-id="213fc-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="213fc-117">指定类型时，必须用括号括住类型名称和变量名称，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="213fc-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="213fc-118">示例</span><span class="sxs-lookup"><span data-stu-id="213fc-118">Example</span></span>  
 <span data-ttu-id="213fc-119">以下示例演示如何为使用 2 个参数的标准查询运算符 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 的重载编写一个 Lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="213fc-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="213fc-120">由于 Lambda 表达式具有多个参数，因此参数必须括在括号中。</span><span class="sxs-lookup"><span data-stu-id="213fc-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="213fc-121">第 2 个参数 `index` 表示集合中当前元素的索引。</span><span class="sxs-lookup"><span data-stu-id="213fc-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="213fc-122">`Where` 表达式返回长度小于其数组中索引位置的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="213fc-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
## <a name="expression-body-definition"></a><span data-ttu-id="213fc-123">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="213fc-123">Expression body definition</span></span>

<span data-ttu-id="213fc-124">表达式主体定义提供高度压缩，可读的窗体中的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="213fc-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="213fc-125">它具有以下常规语法：</span><span class="sxs-lookup"><span data-stu-id="213fc-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="213fc-126">其中“expression”是有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="213fc-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="213fc-127">请注意，*表达式*可以是*语句表达式*仅当成员的返回类型是`void`，或如果该成员是一个构造函数或终结器。</span><span class="sxs-lookup"><span data-stu-id="213fc-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="213fc-128">从 C# 6 支持的方法和属性 get 语句的表达式主体定义。</span><span class="sxs-lookup"><span data-stu-id="213fc-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="213fc-129">表达式主体定义构造函数，终结器，设置属性的语句，并且支持从 C# 7 开始的索引器。</span><span class="sxs-lookup"><span data-stu-id="213fc-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="213fc-130">以下是表达式主体定义`Person.ToString`方法：</span><span class="sxs-lookup"><span data-stu-id="213fc-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="213fc-131">它是以下方法定义的速记版：</span><span class="sxs-lookup"><span data-stu-id="213fc-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="213fc-132">有关更多详细信息表达式主体定义，请参阅[表达式正文成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)。</span><span class="sxs-lookup"><span data-stu-id="213fc-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="213fc-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="213fc-133">See Also</span></span>  
<span data-ttu-id="213fc-134">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="213fc-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="213fc-135">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="213fc-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
<span data-ttu-id="213fc-136">[Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="213fc-136">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
<span data-ttu-id="213fc-137">[表达式正文成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)。</span><span class="sxs-lookup"><span data-stu-id="213fc-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>