---
title: "如何︰ 执行表达式树 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4cc2c9890c1f5efbc4036d94eef1adb05094ae40
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="8daf9-102">如何︰ 执行表达式树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8daf9-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="8daf9-103">本主题演示如何执行表达式树。</span><span class="sxs-lookup"><span data-stu-id="8daf9-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="8daf9-104">执行表达式树可能会返回一个值，或者它可能只需执行的操作，例如调用方法。</span><span class="sxs-lookup"><span data-stu-id="8daf9-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="8daf9-105">可以执行仅表示 lambda 表达式的表达式树。</span><span class="sxs-lookup"><span data-stu-id="8daf9-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="8daf9-106">表示 lambda 表达式的表达式目录树是类型<xref:System.Linq.Expressions.LambdaExpression>或<xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="8daf9-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="8daf9-107">若要执行这些表达式树，调用<xref:System.Linq.Expressions.LambdaExpression.Compile%2A>方法来创建一个可执行的委托，然后调用该委托。</xref:System.Linq.Expressions.LambdaExpression.Compile%2A></span><span class="sxs-lookup"><span data-stu-id="8daf9-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8daf9-108">如果不知道该委托的类型，即 lambda 表达式是类型<xref:System.Linq.Expressions.LambdaExpression>和 not <xref:System.Linq.Expressions.Expression%601>，必须调用<xref:System.Delegate.DynamicInvoke%2A>上而不是直接调用委托方法。</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="8daf9-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="8daf9-109">如果表达式目录树不表示 lambda 表达式，可以创建一个新的 lambda 表达式作为其主体具有原始表达式目录树，通过调用<xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>方法。</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29></span><span class="sxs-lookup"><span data-stu-id="8daf9-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="8daf9-110">然后，可以执行 lambda 表达式，如本节前面所述。</span><span class="sxs-lookup"><span data-stu-id="8daf9-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8daf9-111">示例</span><span class="sxs-lookup"><span data-stu-id="8daf9-111">Example</span></span>  
 <span data-ttu-id="8daf9-112">下面的代码示例演示如何执行表达式树表示数字的幂︰ 创建 lambda 表达式，然后执行它。</span><span class="sxs-lookup"><span data-stu-id="8daf9-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="8daf9-113">结果，它表示为数字幂的次幂，将显示。</span><span class="sxs-lookup"><span data-stu-id="8daf9-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8daf9-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="8daf9-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="8daf9-115">如果未引用将添加对 System.Core.dll 的项目引用。</span><span class="sxs-lookup"><span data-stu-id="8daf9-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="8daf9-116">包括 System.Linq.Expressions 命名空间。</span><span class="sxs-lookup"><span data-stu-id="8daf9-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8daf9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8daf9-117">See Also</span></span>  
 <span data-ttu-id="8daf9-118">[表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="8daf9-118">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="8daf9-119"> [如何︰ 修改表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="8daf9-119"> [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span></span>
