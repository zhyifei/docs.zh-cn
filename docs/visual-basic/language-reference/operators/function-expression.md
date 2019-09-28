---
title: 函数表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 0ab4a77395b478df06f34240212438f3e6e18f6e
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592207"
---
# <a name="function-expression-visual-basic"></a>函数表达式 (Visual Basic)
声明定义函数 lambda 表达式的参数和代码。  
  
## <a name="syntax"></a>语法  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`parameterlist`|可选。 表示此过程参数的局部变量名称的列表。 即使此列表为空，也必须存在括号。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`expression`|必需。 单个表达式。 表达式的类型为函数的返回类型。|  
|`statements`|必需。 通过使用 `Return` 语句返回值的语句列表。 （请参见[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。）返回的值的类型为函数的返回类型。|  
  
## <a name="remarks"></a>备注  
 *Lambda 表达式*是没有名称的函数，用于计算并返回值。 除了作为 `RemoveHandler` 的参数以外，还可以在可以使用委托类型的任何位置使用 lambda 表达式。 有关委托的详细信息以及对委托使用 lambda 表达式的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)和[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。  
  
## <a name="lambda-expression-syntax"></a>Lambda 表达式语法  
 Lambda 表达式的语法与标准函数的语法类似。 不同之处如下：  
  
- Lambda 表达式没有名称。  
  
- Lambda 表达式不能具有修饰符，如 `Overloads` 或 @no__t 为-1。  
  
- Lambda 表达式不使用 `As` 子句来指定函数的返回类型。 相反，该类型是从单行 lambda 表达式的主体计算得出的值推断出的，或是多行 lambda 表达式的返回值。 例如，如果单行 lambda 表达式的主体为 `Where cust.City = "London"`，则其返回类型为 `Boolean`。  
  
- 单行 lambda 表达式的主体必须是表达式，而不是语句。 正文可以包含对 function 过程的调用，但不能包含对 sub 过程的调用。  
  
- 所有参数都必须具有指定的数据类型，或者都必须被推断。  
  
- 不允许使用可选参数和 Paramarray 参数。  
  
- 不允许使用泛型参数。  
  
## <a name="example"></a>示例  
 下面的示例演示了两种创建简单 lambda 表达式的方法。 第一个函数使用 `Dim` 来提供函数的名称。 若要调用函数，请发送参数的值。  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>示例  
 或者，可以同时声明和运行函数。  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>示例  
 下面是递增其参数并返回值的 lambda 表达式的示例。 该示例显示了函数的单行和多行 lambda 表达式语法。 有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a>示例  
 Lambda 表达式的基础是 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 中的许多查询运算符，可以在基于方法的查询中显式使用。 下面的示例演示典型的 @no__t 0 查询，然后将查询转换为方法格式。  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 有关查询方法的详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/index.md)。 有关标准查询运算符的详细信息，请参阅[标准查询运算符概述](../../programming-guide/concepts/linq/standard-query-operators-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
- [值的比较](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
- [宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
