---
title: 函数表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 29bf95a336b6f6ed5c9c310c9ea7575a91089361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="function-expression-visual-basic"></a>函数表达式 (Visual Basic)
声明的参数和定义函数 lambda 表达式的代码。  
  
## <a name="syntax"></a>语法  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`parameterlist`|可选。 表示在此过程中的参数的本地变量名称的列表。 括号必须存在，即使列表为空。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`expression`|必须的。 单个表达式。 表达式的类型是函数的返回类型。|  
|`statements`|必须的。 返回一个值，通过使用的语句列表`Return`语句。 (请参阅[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。)返回的类型是值的函数的返回类型。|  
  
## <a name="remarks"></a>备注  
 A *lambda 表达式*是没有名称，用于计算并返回一个值的函数。 你可以使用 lambda 表达式任意位置可用作委托类型，除外的自变量`RemoveHandler`。 有关委托，而使用与委托的 lambda 表达式的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)和[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。  
  
## <a name="lambda-expression-syntax"></a>Lambda 表达式语法  
 Lambda 表达式的语法类似于标准函数。 差异如下所示：  
  
-   Lambda 表达式不具有名称。  
  
-   Lambda 表达式不能具有修饰符，如`Overloads`或`Overrides`。  
  
-   不使用 lambda 表达式`As`子句来指定函数的返回类型。 相反，从单行 lambda 表达式的主体，计算得出的值或多行 lambda 表达式的返回值推断的类型。 例如，如果单行 lambda 表达式的主体是`Where cust.City = "London"`，其返回类型是`Boolean`。  
  
-   单行 lambda 表达式的主体必须是一个表达式，而不是语句。 主体可以包含的调用函数的过程，但未对 sub 过程的调用。  
  
-   必须必须推断数据类型或所有具有指定任一所有参数。  
  
-   不允许使用可选和 Paramarray 参数。  
  
-   不允许泛型参数。  
  
## <a name="example"></a>示例  
 下面的示例演示两种方法创建的简单 lambda 表达式。 第一个示例使用`Dim`提供函数的名称。 若要调用函数，您传递参数的值。  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>示例  
 或者，你可以声明并在同一时间运行此函数。  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>示例  
 下面是递增其参数并返回的值的 lambda 表达式的示例。 该示例演示这两个单行和多行 lambda 表达式语法的函数。 有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>示例  
 Lambda 表达式生成的查询运算符中的许多[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]，并可以在基于方法的查询中显式使用。 以下示例演示一个典型[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询，为方法格式跟查询的转换。  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 有关查询方法的详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/queries.md)。 有关标准查询运算符的详细信息，请参阅[标准查询运算符概述](../../programming-guide/concepts/linq/standard-query-operators-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)  
 [值的比较](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)  
 [宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
