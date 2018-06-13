---
title: 如何：执行表达式树 (C#)
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: 0ebdcb603a1adf3602e897db284faa2f75b7de7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322086"
---
# <a name="how-to-execute-expression-trees-c"></a><span data-ttu-id="1708c-102">如何：执行表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="1708c-102">How to: Execute Expression Trees (C#)</span></span>
<span data-ttu-id="1708c-103">本主题演示如何执行表达式树。</span><span class="sxs-lookup"><span data-stu-id="1708c-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="1708c-104">执行表达式树可能返回一个值，或者它可能只是执行操作，例如调用方法。</span><span class="sxs-lookup"><span data-stu-id="1708c-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="1708c-105">仅可以执行表示 lambda 表达式的表达式树。</span><span class="sxs-lookup"><span data-stu-id="1708c-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="1708c-106">表示 Lambda 表达式的表达式树的类型为 <xref:System.Linq.Expressions.LambdaExpression> 或 <xref:System.Linq.Expressions.Expression%601>。</span><span class="sxs-lookup"><span data-stu-id="1708c-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="1708c-107">若要执行这些表达式树，请调用 <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> 方法来创建一个可执行的委托，然后调用该委托。</span><span class="sxs-lookup"><span data-stu-id="1708c-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1708c-108">如果委托的类型未知，也就是说 Lambda 表达式的类型为 <xref:System.Linq.Expressions.LambdaExpression>，而不是 <xref:System.Linq.Expressions.Expression%601>，则必须对委托调用 <xref:System.Delegate.DynamicInvoke%2A> 方法，而不是直接调用委托。</span><span class="sxs-lookup"><span data-stu-id="1708c-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="1708c-109">如果表达式树不表示 Lambda 表达式，可以通过调用 <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> 方法创建一个新的 Lambda 表达式，此表达式的主体为原始表达式树。</span><span class="sxs-lookup"><span data-stu-id="1708c-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="1708c-110">然后，按本节前面所述执行此 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="1708c-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1708c-111">示例</span><span class="sxs-lookup"><span data-stu-id="1708c-111">Example</span></span>  
 <span data-ttu-id="1708c-112">下面的代码示例演示如何通过创建 lambda 表达式并执行它来执行代表幂运算的表达式树。</span><span class="sxs-lookup"><span data-stu-id="1708c-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="1708c-113">示例最后显示幂运算的结果。</span><span class="sxs-lookup"><span data-stu-id="1708c-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1708c-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="1708c-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1708c-115">添加对 System.Core.dll 的项目引用（如果尚未引用）。</span><span class="sxs-lookup"><span data-stu-id="1708c-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="1708c-116">包括 System.Linq.Expressions 命名空间。</span><span class="sxs-lookup"><span data-stu-id="1708c-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1708c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1708c-117">See Also</span></span>  
 [<span data-ttu-id="1708c-118">表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="1708c-118">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="1708c-119">如何：修改表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="1708c-119">How to: Modify Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
