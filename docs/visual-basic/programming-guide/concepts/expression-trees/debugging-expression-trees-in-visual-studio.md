---
title: "调试 Visual Studio (Visual Basic 中) 中的表达式树 |Microsoft 文档"
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
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84de749afad6abb748d0622561f8ee7cd399ed54
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="afde3-102">调试 Visual Studio (Visual Basic 中) 中的表达式树</span><span class="sxs-lookup"><span data-stu-id="afde3-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="afde3-103">在调试您的应用程序时，可以分析结构和内容的表达式树。</span><span class="sxs-lookup"><span data-stu-id="afde3-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="afde3-104">若要获取的简单表达式树结构概述，可以使用`DebugView`属性，它是仅在调试模式中可用。</span><span class="sxs-lookup"><span data-stu-id="afde3-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="afde3-105">有关调试的详细信息，请参阅[Visual Studio 中调试](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="afde3-105">For more information about debugging, see [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="afde3-106">若要更好地表示表达式树的内容`DebugView`属性使用 Visual Studio 可视化工具。</span><span class="sxs-lookup"><span data-stu-id="afde3-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="afde3-107">有关详细信息，请参阅[创建自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)。</span><span class="sxs-lookup"><span data-stu-id="afde3-107">For more information, see [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="afde3-108">若要打开表达式目录树的可视化工具</span><span class="sxs-lookup"><span data-stu-id="afde3-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="afde3-109">单击放大镜图标旁边显示`DebugView`表达式树中的属性**数据提示**、**监视**窗口中，**自动**窗口中，或**局部变量**窗口。</span><span class="sxs-lookup"><span data-stu-id="afde3-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="afde3-110">将会显示可视化工具列表。</span><span class="sxs-lookup"><span data-stu-id="afde3-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="afde3-111">单击要使用的可视化工具。</span><span class="sxs-lookup"><span data-stu-id="afde3-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="afde3-112">以下各节中所述，可视化工具中显示每个表达式类型。</span><span class="sxs-lookup"><span data-stu-id="afde3-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="afde3-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="afde3-113">ParameterExpressions</span></span>  
 <span data-ttu-id="afde3-114"><xref:System.Linq.Expressions.ParameterExpression>变量的名称将显示使用"$"符号开头。</xref:System.Linq.Expressions.ParameterExpression></span><span class="sxs-lookup"><span data-stu-id="afde3-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="afde3-115">如果参数不具有一个名称，向其分配一个自动生成的名称，如`$var1`或`$var2`。</span><span class="sxs-lookup"><span data-stu-id="afde3-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="afde3-116">示例</span><span class="sxs-lookup"><span data-stu-id="afde3-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="afde3-117">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="afde3-118">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="afde3-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="afde3-119">ConstantExpressions</span></span>  
 <span data-ttu-id="afde3-120">有关<xref:System.Linq.Expressions.ConstantExpression>表示字符串的整数值的对象和`null`，显示常量的值。</xref:System.Linq.Expressions.ConstantExpression></span><span class="sxs-lookup"><span data-stu-id="afde3-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="afde3-121">示例</span><span class="sxs-lookup"><span data-stu-id="afde3-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="afde3-122">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="afde3-123">10</span><span class="sxs-lookup"><span data-stu-id="afde3-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="afde3-124">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="afde3-125">10 个 D</span><span class="sxs-lookup"><span data-stu-id="afde3-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="afde3-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="afde3-126">BlockExpression</span></span>  
 <span data-ttu-id="afde3-127">如果的一种<xref:System.Linq.Expressions.BlockExpression>对象不同于块中的最后一个表达式的类型，该类型将显示在`DebugInfo`尖括号中的属性 (\<和&1;>)。</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="afde3-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="afde3-128">否则为的一种<xref:System.Linq.Expressions.BlockExpression>不显示对象。</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="afde3-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="afde3-129">示例</span><span class="sxs-lookup"><span data-stu-id="afde3-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="afde3-130">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="afde3-131">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="afde3-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="afde3-132">LambdaExpression</span></span>  
 <span data-ttu-id="afde3-133"><xref:System.Linq.Expressions.LambdaExpression>对象会显示以及它们的委托类型。</xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="afde3-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="afde3-134">如果 lambda 表达式不具有一个名称，向其分配一个自动生成的名称，如`#Lambda1`或`#Lambda2`。</span><span class="sxs-lookup"><span data-stu-id="afde3-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="afde3-135">示例</span><span class="sxs-lookup"><span data-stu-id="afde3-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="afde3-136">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="afde3-137">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="afde3-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="afde3-138">LabelExpression</span></span>  
 <span data-ttu-id="afde3-139">如果指定默认值为<xref:System.Linq.Expressions.LabelExpression>对象时，此值显示在之前<xref:System.Linq.Expressions.LabelTarget>对象。</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression></span><span class="sxs-lookup"><span data-stu-id="afde3-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="afde3-140">`.Label`令牌指示标签的开头。</span><span class="sxs-lookup"><span data-stu-id="afde3-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="afde3-141">`.LabelTarget`令牌该值指示要跳转到的目标的目标。</span><span class="sxs-lookup"><span data-stu-id="afde3-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="afde3-142">如果标签不具有一个名称，向其分配一个自动生成的名称，如`#Label1`或`#Label2`。</span><span class="sxs-lookup"><span data-stu-id="afde3-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="afde3-143">示例</span><span class="sxs-lookup"><span data-stu-id="afde3-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="afde3-144">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-144">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     <span data-ttu-id="afde3-145">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="afde3-146">Checked 的运算符</span><span class="sxs-lookup"><span data-stu-id="afde3-146">Checked Operators</span></span>  
 <span data-ttu-id="afde3-147">Checked 的运算符将显示为"#"符号前面运算符。</span><span class="sxs-lookup"><span data-stu-id="afde3-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="afde3-148">例如，检查的加法运算符显示为`#+`。</span><span class="sxs-lookup"><span data-stu-id="afde3-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="afde3-149">示例</span><span class="sxs-lookup"><span data-stu-id="afde3-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="afde3-150">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="afde3-151">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="afde3-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="afde3-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afde3-152">See Also</span></span>  
 <span data-ttu-id="afde3-153">[表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="afde3-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="afde3-154"> [在 Visual Studio 中进行调试](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="afde3-154"> [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="afde3-155"> [创建自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span><span class="sxs-lookup"><span data-stu-id="afde3-155"> [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
