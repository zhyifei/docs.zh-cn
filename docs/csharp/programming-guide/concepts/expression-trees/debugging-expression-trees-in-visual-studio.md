---
title: 在 Visual Studio 中调试表达式树 (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877166"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="d4c70-102">在 Visual Studio 中调试表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="d4c70-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="d4c70-103">可以在调试应用程序时分析表达式树的结构和内容。</span><span class="sxs-lookup"><span data-stu-id="d4c70-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="d4c70-104">要快速了解表达式树结构，可以使用 `DebugView` 属性，该属性使用[以下](#debugview-syntax)所述的特殊语法表示表达式树。</span><span class="sxs-lookup"><span data-stu-id="d4c70-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="d4c70-105">（请注意，`DebugView` 仅在调试模式下可用。）</span><span class="sxs-lookup"><span data-stu-id="d4c70-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Visual Studio 调试器中的表达式树 DebugView](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="d4c70-107">由于 `DebugView` 是一个字符串，因此可以使用[内置文本可视化工具](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)在多行中进行查看，方法是从 `DebugView` 标签旁边的放大镜图标中选择“文本可视化工具”。</span><span class="sxs-lookup"><span data-stu-id="d4c70-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![文本可视化工具应用于“DebugView”的结果](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="d4c70-109">或者，可以为表达式树安装和使用[自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)：</span><span class="sxs-lookup"><span data-stu-id="d4c70-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="d4c70-110">[可读表达式](https://github.com/agileobjects/ReadableExpressions)（[MIT 许可证](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)，可在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) 中获得）将表达式树呈现为 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="d4c70-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![可读表达式可视化工具](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="d4c70-112">[表达式树可视化工具](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees)（[MIT 许可证](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)）提供表达式树、其属性和相关对象的图形视图：</span><span class="sxs-lookup"><span data-stu-id="d4c70-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![ExpressionToString 可视化工具](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="d4c70-114">打开表达式树的可视化工具</span><span class="sxs-lookup"><span data-stu-id="d4c70-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="d4c70-115">单击“数据提示”、“监视”窗口、“自动”窗口或“本地”窗口中表达式树旁边显示的放大镜图标。</span><span class="sxs-lookup"><span data-stu-id="d4c70-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="d4c70-116">显示可用的可视化工具列表：</span><span class="sxs-lookup"><span data-stu-id="d4c70-116">A list of available visualizers is displayed.:</span></span> 

      ![从 Visual Studio 打开可视化工具](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="d4c70-118">单击要使用的可视化工具。</span><span class="sxs-lookup"><span data-stu-id="d4c70-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="d4c70-119">`DebugView` 语法</span><span class="sxs-lookup"><span data-stu-id="d4c70-119">`DebugView` syntax</span></span> 

<span data-ttu-id="d4c70-120">每个表达式类型都由 `DebugView` 属性显示，如以下部分所述。</span><span class="sxs-lookup"><span data-stu-id="d4c70-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="d4c70-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="d4c70-121">ParameterExpressions</span></span>  
 <span data-ttu-id="d4c70-122"><xref:System.Linq.Expressions.ParameterExpression> 变量名称的开头显示有“$”符号。</span><span class="sxs-lookup"><span data-stu-id="d4c70-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="d4c70-123">如果参数没有名称，则会为其分配一个自动生成的名称，例如 `$var1` 或 `$var2`。</span><span class="sxs-lookup"><span data-stu-id="d4c70-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d4c70-124">示例</span><span class="sxs-lookup"><span data-stu-id="d4c70-124">Examples</span></span>  
  
|<span data-ttu-id="d4c70-125">表达式</span><span class="sxs-lookup"><span data-stu-id="d4c70-125">Expression</span></span>|<span data-ttu-id="d4c70-126">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="d4c70-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="d4c70-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="d4c70-127">ConstantExpressions</span></span>  
 <span data-ttu-id="d4c70-128">对于表示整数值、字符串和 `null` 的 <xref:System.Linq.Expressions.ConstantExpression> 对象，将显示常数的值。</span><span class="sxs-lookup"><span data-stu-id="d4c70-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="d4c70-129">对于使用标准后缀作为 C# 原义字符的数值类型，将后缀添加到值。</span><span class="sxs-lookup"><span data-stu-id="d4c70-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="d4c70-130">下表显示与各种数值类型关联的后缀。</span><span class="sxs-lookup"><span data-stu-id="d4c70-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="d4c70-131">类型</span><span class="sxs-lookup"><span data-stu-id="d4c70-131">Type</span></span>|<span data-ttu-id="d4c70-132">后缀</span><span class="sxs-lookup"><span data-stu-id="d4c70-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="d4c70-133">U</span><span class="sxs-lookup"><span data-stu-id="d4c70-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="d4c70-134">L</span><span class="sxs-lookup"><span data-stu-id="d4c70-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="d4c70-135">UL</span><span class="sxs-lookup"><span data-stu-id="d4c70-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="d4c70-136">D</span><span class="sxs-lookup"><span data-stu-id="d4c70-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="d4c70-137">F</span><span class="sxs-lookup"><span data-stu-id="d4c70-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="d4c70-138">M</span><span class="sxs-lookup"><span data-stu-id="d4c70-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="d4c70-139">示例</span><span class="sxs-lookup"><span data-stu-id="d4c70-139">Examples</span></span>  
  
|<span data-ttu-id="d4c70-140">表达式</span><span class="sxs-lookup"><span data-stu-id="d4c70-140">Expression</span></span>|<span data-ttu-id="d4c70-141">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="d4c70-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="d4c70-142">10</span><span class="sxs-lookup"><span data-stu-id="d4c70-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="d4c70-143">10D</span><span class="sxs-lookup"><span data-stu-id="d4c70-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="d4c70-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="d4c70-144">BlockExpression</span></span>  
 <span data-ttu-id="d4c70-145">如果 <xref:System.Linq.Expressions.BlockExpression> 对象的类型与块中最后一个表达式的类型不同，则该类型将显示在 `DebugInfo` 属性中的尖括号（\< 和 >）中。</span><span class="sxs-lookup"><span data-stu-id="d4c70-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="d4c70-146">否则，将不显示 <xref:System.Linq.Expressions.BlockExpression> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="d4c70-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d4c70-147">示例</span><span class="sxs-lookup"><span data-stu-id="d4c70-147">Examples</span></span>  
  
|<span data-ttu-id="d4c70-148">表达式</span><span class="sxs-lookup"><span data-stu-id="d4c70-148">Expression</span></span>|<span data-ttu-id="d4c70-149">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="d4c70-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="d4c70-150">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="d4c70-150">LambdaExpression</span></span>  
 <span data-ttu-id="d4c70-151">显示 <xref:System.Linq.Expressions.LambdaExpression> 对象及其委托类型。</span><span class="sxs-lookup"><span data-stu-id="d4c70-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="d4c70-152">如果 lambda 表达式没有名称，则会为其分配一个自动生成的名称，例如 `#Lambda1` 或 `#Lambda2`。</span><span class="sxs-lookup"><span data-stu-id="d4c70-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d4c70-153">示例</span><span class="sxs-lookup"><span data-stu-id="d4c70-153">Examples</span></span>  
  
|<span data-ttu-id="d4c70-154">表达式</span><span class="sxs-lookup"><span data-stu-id="d4c70-154">Expression</span></span>|<span data-ttu-id="d4c70-155">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="d4c70-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="d4c70-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="d4c70-156">LabelExpression</span></span>  
 <span data-ttu-id="d4c70-157">如果指定 <xref:System.Linq.Expressions.LabelExpression> 对象的默认值，则在 <xref:System.Linq.Expressions.LabelTarget> 对象之前显示此值。</span><span class="sxs-lookup"><span data-stu-id="d4c70-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="d4c70-158">`.Label` 令牌指示标签的开头。</span><span class="sxs-lookup"><span data-stu-id="d4c70-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="d4c70-159">`.LabelTarget` 令牌指示要跳转到的目标的目的地。</span><span class="sxs-lookup"><span data-stu-id="d4c70-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="d4c70-160">如果标签没有名称，则会为其分配一个自动生成的名称，例如 `#Label1` 或 `#Label2`。</span><span class="sxs-lookup"><span data-stu-id="d4c70-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d4c70-161">示例</span><span class="sxs-lookup"><span data-stu-id="d4c70-161">Examples</span></span>  
  
|<span data-ttu-id="d4c70-162">表达式</span><span class="sxs-lookup"><span data-stu-id="d4c70-162">Expression</span></span>|<span data-ttu-id="d4c70-163">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="d4c70-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="d4c70-164">Checked 运算符</span><span class="sxs-lookup"><span data-stu-id="d4c70-164">Checked Operators</span></span>  
 <span data-ttu-id="d4c70-165">Checked 运算符在运算符前面显示 “#” 符号。</span><span class="sxs-lookup"><span data-stu-id="d4c70-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="d4c70-166">例如，checked 加号显示为 `#+`。</span><span class="sxs-lookup"><span data-stu-id="d4c70-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d4c70-167">示例</span><span class="sxs-lookup"><span data-stu-id="d4c70-167">Examples</span></span>  
  
|<span data-ttu-id="d4c70-168">表达式</span><span class="sxs-lookup"><span data-stu-id="d4c70-168">Expression</span></span>|<span data-ttu-id="d4c70-169">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="d4c70-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="d4c70-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c70-170">See also</span></span>

- [<span data-ttu-id="d4c70-171">表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="d4c70-171">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="d4c70-172">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="d4c70-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="d4c70-173">创建自定义可视化工具</span><span class="sxs-lookup"><span data-stu-id="d4c70-173">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
