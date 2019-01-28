---
title: 在 Visual Studio 中调试表达式树 (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 308b377af00a3d12523f8f8d469c50808f216030
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632148"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="e9b48-102">在 Visual Studio 中调试表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="e9b48-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="e9b48-103">可以在调试应用程序时分析表达式树的结构和内容。</span><span class="sxs-lookup"><span data-stu-id="e9b48-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="e9b48-104">若要快速了解表达式树结构，可以使用 `DebugView` 属性，该属性仅在调试模式下可用。</span><span class="sxs-lookup"><span data-stu-id="e9b48-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="e9b48-105">有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="e9b48-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="e9b48-106">为了更好地表示表达式树的内容，`DebugView` 属性使用 Visual Studio 可视化工具。</span><span class="sxs-lookup"><span data-stu-id="e9b48-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="e9b48-107">有关详细信息，请参阅[创建自定义可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)。</span><span class="sxs-lookup"><span data-stu-id="e9b48-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="e9b48-108">打开表达式树的可视化工具</span><span class="sxs-lookup"><span data-stu-id="e9b48-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="e9b48-109">单击“数据提示”、“监视”窗口、“自动”或“局部变量”窗口中表达式树的 `DebugView` 属性旁边显示的放大镜图标。</span><span class="sxs-lookup"><span data-stu-id="e9b48-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="e9b48-110">将会显示可视化工具列表。</span><span class="sxs-lookup"><span data-stu-id="e9b48-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="e9b48-111">单击要使用的可视化工具。</span><span class="sxs-lookup"><span data-stu-id="e9b48-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="e9b48-112">每个表达式类型如以下各节所述显示在可视化工具中。</span><span class="sxs-lookup"><span data-stu-id="e9b48-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="e9b48-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="e9b48-113">ParameterExpressions</span></span>  
 <span data-ttu-id="e9b48-114"><xref:System.Linq.Expressions.ParameterExpression> 变量名称的开头显示有“$”符号。</span><span class="sxs-lookup"><span data-stu-id="e9b48-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="e9b48-115">如果参数没有名称，则会为其分配一个自动生成的名称，例如 `$var1` 或 `$var2`。</span><span class="sxs-lookup"><span data-stu-id="e9b48-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e9b48-116">示例</span><span class="sxs-lookup"><span data-stu-id="e9b48-116">Examples</span></span>  
  
|<span data-ttu-id="e9b48-117">表达式</span><span class="sxs-lookup"><span data-stu-id="e9b48-117">Expression</span></span>|<span data-ttu-id="e9b48-118">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="e9b48-118">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="e9b48-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="e9b48-119">ConstantExpressions</span></span>  
 <span data-ttu-id="e9b48-120">对于表示整数值、字符串和 `null` 的 <xref:System.Linq.Expressions.ConstantExpression> 对象，将显示常数的值。</span><span class="sxs-lookup"><span data-stu-id="e9b48-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="e9b48-121">对于使用标准后缀作为 C# 原义字符的数值类型，将后缀添加到值。</span><span class="sxs-lookup"><span data-stu-id="e9b48-121">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="e9b48-122">下表显示与各种数值类型关联的后缀。</span><span class="sxs-lookup"><span data-stu-id="e9b48-122">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="e9b48-123">类型</span><span class="sxs-lookup"><span data-stu-id="e9b48-123">Type</span></span>|<span data-ttu-id="e9b48-124">后缀</span><span class="sxs-lookup"><span data-stu-id="e9b48-124">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="e9b48-125">U</span><span class="sxs-lookup"><span data-stu-id="e9b48-125">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="e9b48-126">L</span><span class="sxs-lookup"><span data-stu-id="e9b48-126">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="e9b48-127">UL</span><span class="sxs-lookup"><span data-stu-id="e9b48-127">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="e9b48-128">D</span><span class="sxs-lookup"><span data-stu-id="e9b48-128">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="e9b48-129">F</span><span class="sxs-lookup"><span data-stu-id="e9b48-129">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="e9b48-130">M</span><span class="sxs-lookup"><span data-stu-id="e9b48-130">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="e9b48-131">示例</span><span class="sxs-lookup"><span data-stu-id="e9b48-131">Examples</span></span>  
  
|<span data-ttu-id="e9b48-132">表达式</span><span class="sxs-lookup"><span data-stu-id="e9b48-132">Expression</span></span>|<span data-ttu-id="e9b48-133">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="e9b48-133">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="e9b48-134">10</span><span class="sxs-lookup"><span data-stu-id="e9b48-134">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="e9b48-135">10D</span><span class="sxs-lookup"><span data-stu-id="e9b48-135">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="e9b48-136">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="e9b48-136">BlockExpression</span></span>  
 <span data-ttu-id="e9b48-137">如果 <xref:System.Linq.Expressions.BlockExpression> 对象的类型与块中最后一个表达式的类型不同，则该类型将显示在 `DebugInfo` 属性中的尖括号（\< 和 >）中。</span><span class="sxs-lookup"><span data-stu-id="e9b48-137">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="e9b48-138">否则，将不显示 <xref:System.Linq.Expressions.BlockExpression> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="e9b48-138">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e9b48-139">示例</span><span class="sxs-lookup"><span data-stu-id="e9b48-139">Examples</span></span>  
  
|<span data-ttu-id="e9b48-140">表达式</span><span class="sxs-lookup"><span data-stu-id="e9b48-140">Expression</span></span>|<span data-ttu-id="e9b48-141">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="e9b48-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="e9b48-142">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="e9b48-142">LambdaExpression</span></span>  
 <span data-ttu-id="e9b48-143">显示 <xref:System.Linq.Expressions.LambdaExpression> 对象及其委托类型。</span><span class="sxs-lookup"><span data-stu-id="e9b48-143"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="e9b48-144">如果 lambda 表达式没有名称，则会为其分配一个自动生成的名称，例如 `#Lambda1` 或 `#Lambda2`。</span><span class="sxs-lookup"><span data-stu-id="e9b48-144">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e9b48-145">示例</span><span class="sxs-lookup"><span data-stu-id="e9b48-145">Examples</span></span>  
  
|<span data-ttu-id="e9b48-146">表达式</span><span class="sxs-lookup"><span data-stu-id="e9b48-146">Expression</span></span>|<span data-ttu-id="e9b48-147">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="e9b48-147">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="e9b48-148">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="e9b48-148">LabelExpression</span></span>  
 <span data-ttu-id="e9b48-149">如果指定 <xref:System.Linq.Expressions.LabelExpression> 对象的默认值，则在 <xref:System.Linq.Expressions.LabelTarget> 对象之前显示此值。</span><span class="sxs-lookup"><span data-stu-id="e9b48-149">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="e9b48-150">`.Label` 令牌指示标签的开头。</span><span class="sxs-lookup"><span data-stu-id="e9b48-150">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="e9b48-151">`.LabelTarget` 令牌指示要跳转到的目标的目的地。</span><span class="sxs-lookup"><span data-stu-id="e9b48-151">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="e9b48-152">如果标签没有名称，则会为其分配一个自动生成的名称，例如 `#Label1` 或 `#Label2`。</span><span class="sxs-lookup"><span data-stu-id="e9b48-152">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e9b48-153">示例</span><span class="sxs-lookup"><span data-stu-id="e9b48-153">Examples</span></span>  
  
|<span data-ttu-id="e9b48-154">表达式</span><span class="sxs-lookup"><span data-stu-id="e9b48-154">Expression</span></span>|<span data-ttu-id="e9b48-155">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="e9b48-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="e9b48-156">Checked 运算符</span><span class="sxs-lookup"><span data-stu-id="e9b48-156">Checked Operators</span></span>  
 <span data-ttu-id="e9b48-157">Checked 运算符在运算符前面显示 “#” 符号。</span><span class="sxs-lookup"><span data-stu-id="e9b48-157">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="e9b48-158">例如，checked 加号显示为 `#+`。</span><span class="sxs-lookup"><span data-stu-id="e9b48-158">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="e9b48-159">示例</span><span class="sxs-lookup"><span data-stu-id="e9b48-159">Examples</span></span>  
  
|<span data-ttu-id="e9b48-160">表达式</span><span class="sxs-lookup"><span data-stu-id="e9b48-160">Expression</span></span>|<span data-ttu-id="e9b48-161">`DebugView` 属性</span><span class="sxs-lookup"><span data-stu-id="e9b48-161">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="e9b48-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9b48-162">See also</span></span>

- [<span data-ttu-id="e9b48-163">表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="e9b48-163">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="e9b48-164">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="e9b48-164">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="e9b48-165">创建自定义可视化工具</span><span class="sxs-lookup"><span data-stu-id="e9b48-165">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
