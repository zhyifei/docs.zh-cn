---
title: "如何：在查询中使用 Lambda 表达式（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
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
ms.openlocfilehash: 5ad819a0e4d441f6ea092480544195b89e0796ca
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="a6c0b-102">如何：在查询中使用 Lambda 表达式（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a6c0b-102">How to: Use Lambda Expressions in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="a6c0b-103">不会直接在查询语法中使用 lambda 表达式，而是在方法调用中使用它们，并且查询表达式可以包含方法调用。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-103">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="a6c0b-104">事实上，一些查询操作只能采用方法语法进行表示。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-104">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="a6c0b-105">有关查询语法与方法语法之间的差异的详细信息，请参阅 [LINQ 中的查询语法和方法语法](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-105">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c0b-106">示例</span><span class="sxs-lookup"><span data-stu-id="a6c0b-106">Example</span></span>  
 <span data-ttu-id="a6c0b-107">下面的示例演示如何通过 <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> 标准查询运算符，在基于方法的查询中使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-107">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> standard query operator.</span></span> <span data-ttu-id="a6c0b-108">请注意，此示例中的 <xref:System.Linq.Enumerable.Where%2A> 方法具有一个 <xref:System.Func%601> 委托类型的输入参数，该委托采用整数作为输入并返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-108">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%601> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="a6c0b-109">Lambda 表达式可以转换为该委托。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-109">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="a6c0b-110">如果这是使用 <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName> 方法的 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 查询，则参数类型会是 `Expression<Func\<int,bool>>`，但 lambda 表达式看起来完全相同。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-110">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName> method, the parameter type would be an `Expression<Func\<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="a6c0b-111">有关表达式类型的详细信息，请参阅 <xref:System.Linq.Expressions.Expression?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-111">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="a6c0b-112">[!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a6c0b-112">[!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c0b-113">示例</span><span class="sxs-lookup"><span data-stu-id="a6c0b-113">Example</span></span>  
 <span data-ttu-id="a6c0b-114">下面的示例演示如何在查询表达式的方法调用中使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-114">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="a6c0b-115">需要 lambda 的原因是无法使用查询语法调用 <xref:System.Linq.Enumerable.Sum%2A> 标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-115">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="a6c0b-116">查询首先根据学生的年级（在 `GradeLevel` 枚举中定义）对学生进行分组。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-116">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="a6c0b-117">然后为每个组添加每个学生的总分。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-117">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="a6c0b-118">这需要两个 `Sum` 操作。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-118">This requires two `Sum` operations.</span></span> <span data-ttu-id="a6c0b-119">内部 `Sum` 为每个学生计算总分，而外部 `Sum` 保留组中所有学生的正在运行的合并总分。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-119">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 <span data-ttu-id="a6c0b-120">[!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a6c0b-120">[!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6c0b-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="a6c0b-121">Compiling the Code</span></span>  
 <span data-ttu-id="a6c0b-122">若要运行此代码，请将方法复制并粘贴到[如何：查询对象的集合](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)中提供的 `StudentClass` 中，然后从 `Main` 方法调用它。</span><span class="sxs-lookup"><span data-stu-id="a6c0b-122">To run this code, copy and paste the method into the `StudentClass` that is provided in [How to: Query a Collection of Objects](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c0b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c0b-123">See Also</span></span>  
 <span data-ttu-id="a6c0b-124">[Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="a6c0b-124">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 [<span data-ttu-id="a6c0b-125">表达式树</span><span class="sxs-lookup"><span data-stu-id="a6c0b-125">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)

