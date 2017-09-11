---
title: "如何︰ 修改表达式树 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
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
ms.openlocfilehash: 2f0d383cbac639212519177fb1825875682f6233
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="367cc-102">如何︰ 修改表达式树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="367cc-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="367cc-103">本主题演示如何修改某个表达式树。</span><span class="sxs-lookup"><span data-stu-id="367cc-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="367cc-104">表达式树是不可变的这意味着它们不能直接修改。</span><span class="sxs-lookup"><span data-stu-id="367cc-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="367cc-105">若要更改表达式目录树，必须创建一份现有表达式树，并在创建该副本，进行必要的更改。</span><span class="sxs-lookup"><span data-stu-id="367cc-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="367cc-106">您可以使用<xref:System.Linq.Expressions.ExpressionVisitor>类遍历现有表达式树，并复制它访问的每个节点。</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="367cc-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="367cc-107">若要修改某个表达式树</span><span class="sxs-lookup"><span data-stu-id="367cc-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="367cc-108">创建一个新**控制台应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="367cc-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="367cc-109">添加`Imports`语句的文件与`System.Linq.Expressions`命名空间。</span><span class="sxs-lookup"><span data-stu-id="367cc-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="367cc-110">添加`AndAlsoModifier`类传递给您的项目。</span><span class="sxs-lookup"><span data-stu-id="367cc-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="367cc-111">此类继承<xref:System.Linq.Expressions.ExpressionVisitor>类，专用于修改表示条件的表达式`AND`operations。</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="367cc-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="367cc-112">它将从条件更改这些操作`AND`为条件`OR`。</span><span class="sxs-lookup"><span data-stu-id="367cc-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="367cc-113">若要这样做，类将重写<xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>方法是基类型，因为条件`AND`表达式表示为二进制表达式。</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A></span><span class="sxs-lookup"><span data-stu-id="367cc-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="367cc-114">在`VisitBinary`方法时，如果传递给它的表达式表示条件`AND`操作，该代码构造一个新的表达式包含条件`OR`运算符而不是在条件`AND`运算符。</span><span class="sxs-lookup"><span data-stu-id="367cc-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="367cc-115">如果传递给该表达式`VisitBinary`不表示条件`AND`操作，该方法交由基类实现。</span><span class="sxs-lookup"><span data-stu-id="367cc-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="367cc-116">就像在中，传递的表达式目录树的构造节点但这些节点将它们替换为表达式树的子树将基类方法生成以递归方式访问者。</span><span class="sxs-lookup"><span data-stu-id="367cc-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="367cc-117">添加`Imports`语句的文件与`System.Linq.Expressions`命名空间。</span><span class="sxs-lookup"><span data-stu-id="367cc-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="367cc-118">将代码添加到`Main`Module1.vb 文件创建一个表达式树并将其传递给该方法的方法中将对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="367cc-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     <span data-ttu-id="367cc-119">该代码创建一个表达式，包含在条件`AND`操作。</span><span class="sxs-lookup"><span data-stu-id="367cc-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="367cc-120">然后，它创建的实例`AndAlsoModifier`类，并将表达式传递给`Modify`此类的方法。</span><span class="sxs-lookup"><span data-stu-id="367cc-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="367cc-121">输出的原始版本以及修改后的表达式树以显示更改。</span><span class="sxs-lookup"><span data-stu-id="367cc-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="367cc-122">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="367cc-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367cc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="367cc-123">See Also</span></span>  
 <span data-ttu-id="367cc-124">[如何︰ 执行表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="367cc-124">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
<span data-ttu-id="367cc-125"> [表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span><span class="sxs-lookup"><span data-stu-id="367cc-125"> [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
