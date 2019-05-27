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
# <a name="debugging-expression-trees-in-visual-studio-c"></a>在 Visual Studio 中调试表达式树 (C#)
可以在调试应用程序时分析表达式树的结构和内容。 要快速了解表达式树结构，可以使用 `DebugView` 属性，该属性使用[以下](#debugview-syntax)所述的特殊语法表示表达式树。 （请注意，`DebugView` 仅在调试模式下可用。）  

![Visual Studio 调试器中的表达式树 DebugView](media/debugging-expression-trees-in-visual-studio/debugview.png)

由于 `DebugView` 是一个字符串，因此可以使用[内置文本可视化工具](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)在多行中进行查看，方法是从 `DebugView` 标签旁边的放大镜图标中选择“文本可视化工具”。

 ![文本可视化工具应用于“DebugView”的结果](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

或者，可以为表达式树安装和使用[自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)：

* [可读表达式](https://github.com/agileobjects/ReadableExpressions)（[MIT 许可证](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)，可在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) 中获得）将表达式树呈现为 C# 代码：

  ![可读表达式可视化工具](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [表达式树可视化工具](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees)（[MIT 许可证](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)）提供表达式树、其属性和相关对象的图形视图：

  ![ExpressionToString 可视化工具](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>打开表达式树的可视化工具  
  
1. 单击“数据提示”、“监视”窗口、“自动”窗口或“本地”窗口中表达式树旁边显示的放大镜图标。  
  
     显示可用的可视化工具列表： 

      ![从 Visual Studio 打开可视化工具](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. 单击要使用的可视化工具。  

## <a name="debugview-syntax"></a>`DebugView` 语法 

每个表达式类型都由 `DebugView` 属性显示，如以下部分所述。  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 <xref:System.Linq.Expressions.ParameterExpression> 变量名称的开头显示有“$”符号。  
  
 如果参数没有名称，则会为其分配一个自动生成的名称，例如 `$var1` 或 `$var2`。  
  
### <a name="examples"></a>示例  
  
|表达式|`DebugView` 属性|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 对于表示整数值、字符串和 `null` 的 <xref:System.Linq.Expressions.ConstantExpression> 对象，将显示常数的值。  
  
 对于使用标准后缀作为 C# 原义字符的数值类型，将后缀添加到值。 下表显示与各种数值类型关联的后缀。  
  
|类型|后缀|  
|----------|------------|  
|<xref:System.UInt32>|U|  
|<xref:System.Int64>|L|  
|<xref:System.UInt64>|UL|  
|<xref:System.Double>|D|  
|<xref:System.Single>|F|  
|<xref:System.Decimal>|M|  
  
### <a name="examples"></a>示例  
  
|表达式|`DebugView` 属性|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|10|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|10D|  
  
## <a name="blockexpression"></a>BlockExpression  
 如果 <xref:System.Linq.Expressions.BlockExpression> 对象的类型与块中最后一个表达式的类型不同，则该类型将显示在 `DebugInfo` 属性中的尖括号（\< 和 >）中。 否则，将不显示 <xref:System.Linq.Expressions.BlockExpression> 对象的类型。  
  
### <a name="examples"></a>示例  
  
|表达式|`DebugView` 属性|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a>LambdaExpression  
 显示 <xref:System.Linq.Expressions.LambdaExpression> 对象及其委托类型。  
  
 如果 lambda 表达式没有名称，则会为其分配一个自动生成的名称，例如 `#Lambda1` 或 `#Lambda2`。  
  
### <a name="examples"></a>示例  
  
|表达式|`DebugView` 属性|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a>LabelExpression  
 如果指定 <xref:System.Linq.Expressions.LabelExpression> 对象的默认值，则在 <xref:System.Linq.Expressions.LabelTarget> 对象之前显示此值。  
  
 `.Label` 令牌指示标签的开头。 `.LabelTarget` 令牌指示要跳转到的目标的目的地。  
  
 如果标签没有名称，则会为其分配一个自动生成的名称，例如 `#Label1` 或 `#Label2`。  
  
### <a name="examples"></a>示例  
  
|表达式|`DebugView` 属性|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a>Checked 运算符  
 Checked 运算符在运算符前面显示 “#” 符号。 例如，checked 加号显示为 `#+`。  
  
### <a name="examples"></a>示例  
  
|表达式|`DebugView` 属性|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a>请参阅

- [表达式树 (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)
- [创建自定义可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)
