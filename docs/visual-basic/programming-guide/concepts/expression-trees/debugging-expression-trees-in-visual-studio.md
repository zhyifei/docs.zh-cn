---
title: Visual Studio (Visual Basic 中) 中调试表达式树
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879832"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio (Visual Basic 中) 中调试表达式树
可以在调试应用程序时分析表达式树的结构和内容。 若要获取表达式树结构的快速概述，可以使用`DebugView`属性，它表示使用所述的特殊语法的表达式树[如下](#debugview-syntax)。 (请注意，`DebugView`仅在调试模式中可用。)  

![DebugView 中的 Visual Studio 调试器中的表达式树](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

由于`DebugView`是一个字符串，可以使用[内置文本可视化工具](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)若要通过选择查看跨多个行**文本可视化工具**旁边的放大镜图标从`DebugView`标签。

 ![文本可视化工具应用于 DebugView 的结果](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

或者，你可以安装并使用[自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)表达式树：

* [可读的表达式](https://github.com/agileobjects/ReadableExpressions)([MIT 许可证](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)，位于[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers))，将呈现为表达式树C#代码：

  ![可读表达式可视化工具](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [表达式树可视化工具](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees)([MIT 许可证](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE))，并提供的表达式树、 其属性和相关的对象; 图形视图还可以呈现 Visual Basic 代码的表达式目录树：

  ![ExpressionToString 可视化工具](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>打开表达式树的可视化工具  
  
1. 单击放大镜图标旁边的表达式树中显示**数据提示**即**监视**窗口中，**自动**窗口中，或**局部变量**窗口。  
  
     显示可用的可视化工具的列表。: 

      ![从 Visual Studio 打开可视化工具](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. 单击要使用的可视化工具。  

## <a name="debugview-syntax"></a>`DebugView` 语法 

每个表达式类型如以下各节所述显示在可视化工具中。

## <a name="parameterexpressions"></a>ParameterExpressions

<xref:System.Linq.Expressions.ParameterExpression> 变量名称的开头显示有“$”符号。

如果参数没有名称，则会为其分配一个自动生成的名称，例如 `$var1` 或 `$var2`。

### <a name="examples"></a>示例

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    `DebugView` 属性

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    `DebugView` 属性

    `$var1`

## <a name="constantexpressions"></a>ConstantExpressions
 对于表示整数值、字符串和 `null` 的 <xref:System.Linq.Expressions.ConstantExpression> 对象，将显示常数的值。

### <a name="examples"></a>示例

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    `DebugView` 属性

    10

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    `DebugView` 属性

    10D

## <a name="blockexpression"></a>BlockExpression

如果 <xref:System.Linq.Expressions.BlockExpression> 对象的类型与块中最后一个表达式的类型不同，则该类型将显示在 `DebugInfo` 属性中的尖括号（\< 和 >）中。 否则，将不显示 <xref:System.Linq.Expressions.BlockExpression> 对象的类型。

### <a name="examples"></a>示例

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    `DebugView` 属性

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    `DebugView` 属性

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a>LambdaExpression

显示 <xref:System.Linq.Expressions.LambdaExpression> 对象及其委托类型。

如果 lambda 表达式没有名称，则会为其分配一个自动生成的名称，例如 `#Lambda1` 或 `#Lambda2`。

### <a name="examples"></a>示例

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    `DebugView` 属性

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    `DebugView` 属性

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a>LabelExpression

如果指定 <xref:System.Linq.Expressions.LabelExpression> 对象的默认值，则在 <xref:System.Linq.Expressions.LabelTarget> 对象之前显示此值。

`.Label` 令牌指示标签的开头。 `.LabelTarget` 令牌指示要跳转到的目标的目的地。

如果标签没有名称，则会为其分配一个自动生成的名称，例如 `#Label1` 或 `#Label2`。

### <a name="examples"></a>示例

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    `DebugView` 属性

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    `DebugView` 属性

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a>Checked 运算符

Checked 运算符在运算符前面显示 “#” 符号。 例如，checked 加号显示为 `#+`。

### <a name="examples"></a>示例

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    `DebugView` 属性

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    `DebugView` 属性

    `#(System.Int32)10D`

## <a name="see-also"></a>请参阅

- [表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)
- [创建自定义可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)
