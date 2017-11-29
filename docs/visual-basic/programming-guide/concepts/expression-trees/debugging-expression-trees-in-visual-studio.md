---
title: "调试 Visual Studio (Visual Basic 中) 中的表达式树"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff1bee9c3c3fdeafab24368d2c7e8376d4ff7b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="62fc1-102">调试 Visual Studio (Visual Basic 中) 中的表达式树</span><span class="sxs-lookup"><span data-stu-id="62fc1-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="62fc1-103">可以在调试应用程序时分析表达式树的结构和内容。</span><span class="sxs-lookup"><span data-stu-id="62fc1-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="62fc1-104">若要快速了解表达式树结构，可以使用 `DebugView` 属性，该属性仅在调试模式下可用。</span><span class="sxs-lookup"><span data-stu-id="62fc1-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="62fc1-105">有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="62fc1-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="62fc1-106">为了更好地表示表达式树的内容，`DebugView` 属性使用 Visual Studio 可视化工具。</span><span class="sxs-lookup"><span data-stu-id="62fc1-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="62fc1-107">有关详细信息，请参阅[创建自定义可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)。</span><span class="sxs-lookup"><span data-stu-id="62fc1-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="62fc1-108">打开表达式树的可视化工具</span><span class="sxs-lookup"><span data-stu-id="62fc1-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="62fc1-109">单击“数据提示”、“监视”窗口、“自动”或“局部变量”窗口中表达式树的 `DebugView` 属性旁边显示的放大镜图标。</span><span class="sxs-lookup"><span data-stu-id="62fc1-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="62fc1-110">将会显示可视化工具列表。</span><span class="sxs-lookup"><span data-stu-id="62fc1-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="62fc1-111">单击要使用的可视化工具。</span><span class="sxs-lookup"><span data-stu-id="62fc1-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="62fc1-112">每个表达式类型如以下各节所述显示在可视化工具中。</span><span class="sxs-lookup"><span data-stu-id="62fc1-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="62fc1-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="62fc1-113">ParameterExpressions</span></span>  
 <span data-ttu-id="62fc1-114"><xref:System.Linq.Expressions.ParameterExpression> 变量名称的开头显示有“$”符号。</span><span class="sxs-lookup"><span data-stu-id="62fc1-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="62fc1-115">如果参数没有名称，则会为其分配一个自动生成的名称，例如 `$var1` 或 `$var2`。</span><span class="sxs-lookup"><span data-stu-id="62fc1-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="62fc1-116">示例</span><span class="sxs-lookup"><span data-stu-id="62fc1-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="62fc1-117">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="62fc1-118">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="62fc1-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="62fc1-119">ConstantExpressions</span></span>  
 <span data-ttu-id="62fc1-120">对于表示整数值、字符串和 `null` 的 <xref:System.Linq.Expressions.ConstantExpression> 对象，将显示常数的值。</span><span class="sxs-lookup"><span data-stu-id="62fc1-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="62fc1-121">示例</span><span class="sxs-lookup"><span data-stu-id="62fc1-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="62fc1-122">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="62fc1-123">10</span><span class="sxs-lookup"><span data-stu-id="62fc1-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="62fc1-124">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="62fc1-125">10D</span><span class="sxs-lookup"><span data-stu-id="62fc1-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="62fc1-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="62fc1-126">BlockExpression</span></span>  
 <span data-ttu-id="62fc1-127">如果 <xref:System.Linq.Expressions.BlockExpression> 对象的类型与块中最后一个表达式的类型不同，则该类型将显示在 `DebugInfo` 属性中的尖括号（\< 和 >）中。</span><span class="sxs-lookup"><span data-stu-id="62fc1-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="62fc1-128">否则，将不显示 <xref:System.Linq.Expressions.BlockExpression> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="62fc1-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="62fc1-129">示例</span><span class="sxs-lookup"><span data-stu-id="62fc1-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="62fc1-130">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="62fc1-131">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="62fc1-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="62fc1-132">LambdaExpression</span></span>  
 <span data-ttu-id="62fc1-133">显示 <xref:System.Linq.Expressions.LambdaExpression> 对象及其委托类型。</span><span class="sxs-lookup"><span data-stu-id="62fc1-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="62fc1-134">如果 lambda 表达式没有名称，则会为其分配一个自动生成的名称，例如 `#Lambda1` 或 `#Lambda2`。</span><span class="sxs-lookup"><span data-stu-id="62fc1-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="62fc1-135">示例</span><span class="sxs-lookup"><span data-stu-id="62fc1-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="62fc1-136">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="62fc1-137">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="62fc1-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="62fc1-138">LabelExpression</span></span>  
 <span data-ttu-id="62fc1-139">如果指定 <xref:System.Linq.Expressions.LabelExpression> 对象的默认值，则在 <xref:System.Linq.Expressions.LabelTarget> 对象之前显示此值。</span><span class="sxs-lookup"><span data-stu-id="62fc1-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="62fc1-140">`.Label` 令牌指示标签的开头。</span><span class="sxs-lookup"><span data-stu-id="62fc1-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="62fc1-141">`.LabelTarget` 令牌指示要跳转到的目标的目的地。</span><span class="sxs-lookup"><span data-stu-id="62fc1-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="62fc1-142">如果标签没有名称，则会为其分配一个自动生成的名称，例如 `#Label1` 或 `#Label2`。</span><span class="sxs-lookup"><span data-stu-id="62fc1-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="62fc1-143">示例</span><span class="sxs-lookup"><span data-stu-id="62fc1-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="62fc1-144">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-144">`DebugView` property</span></span>  
  
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
  
     <span data-ttu-id="62fc1-145">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="62fc1-146">Checked 运算符</span><span class="sxs-lookup"><span data-stu-id="62fc1-146">Checked Operators</span></span>  
 <span data-ttu-id="62fc1-147">Checked 运算符在运算符前面显示 “#” 符号。</span><span class="sxs-lookup"><span data-stu-id="62fc1-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="62fc1-148">例如，checked 加号显示为 `#+`。</span><span class="sxs-lookup"><span data-stu-id="62fc1-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="62fc1-149">示例</span><span class="sxs-lookup"><span data-stu-id="62fc1-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="62fc1-150">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="62fc1-151">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="62fc1-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="62fc1-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62fc1-152">See Also</span></span>  
 [<span data-ttu-id="62fc1-153">表达式树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62fc1-153">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="62fc1-154">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="62fc1-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="62fc1-155">创建自定义可视化工具</span><span class="sxs-lookup"><span data-stu-id="62fc1-155">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
